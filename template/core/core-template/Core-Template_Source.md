---

magic: "UDOC/1"

meta:
  required: [ magic, caster_key, values ]

limits: { hard_min: -2147483648, hard_max: 2147483647 }

defines:
  "4T8G": hard_max
  "-4T8G": hard_min

schema:
  max_hp_default:
    kind: stored
    unit: point
  max_hp_change:
    kind: base
    unit: percent
  max_hp:
    kind: state
    unit: point
  hp:
    kind: state
    unit: point
  lost_hp:
    kind: state
    unit: point

  dps_default:
    kind: stored
    unit: point
  dps_change:
    kind: base
    unit: percent
  dps:
    kind: state
    unit: point

  movement_speed_default:
    kind: stored
    unit: percent
  movement_speed_change:
    kind: base
    unit: percent
  movement_speed:
    kind: state
    unit: percent

  attack_speed_default:
    kind: stored
    unit: percent
  attack_speed_change:
    kind: base
    unit: percent
  attack_speed:
    kind: state
    unit: percent

  projectile_aoe_default:
    kind: stored
    unit: percent   
  projectile_aoe_change:
    kind: base
    unit: percent
  projectile_aoe:
    kind: state
    unit: percent

  projectile_range_default:
    kind: stored
    unit: percent
  projectile_range_change:
    kind: base
    unit: percent
  projectile_range:
    kind: state
    unit: percent

  projectile_speed_default:
    kind: stored
    unit: percent
  projectile_speed_change:
    kind: base
    unit: percent
  projectile_speed:
    kind: state
    unit: percent

use:
  type: object
  required: [ caster, targets, ratio, duration, tick, factor ]
  one_of: [ apply, effect ]
  properties:
    caster:
      type: string
    targets:
      type: array
      items: { type: enum, values: [ ally, enemy ] }
    ratio:
      type: integer
      unit: percent
    duration:
      type: integer
      unit: point
      minimum: 1
    tick:
      type: integer
      unit: point
      minimum: 1
    factor:
      type: integer
      unit: percent
      minimum: 1
    apply:
      type: object
      required: [ holder, source, fixed ]
      properties:
        holder: { type: string }
        source: { type: string }
        fixed: { type: boolean }
    effect:
      type: object
      required: [ stat ]
      properties:
        stat: { type: string }

skills:
  type: map
  key_pattern: "^[a-z][a-z0-9_]*$"
  value:
    type: object
    required: [ parts ]
    properties:
      tags:
        type: array
        items: { type: string }
      parts:
        type: array
        min_items: 1
        items: { type: use }

bursts:
  type: map
  key_pattern: "^[a-z][a-z0-9_]*$"
  value:
    type: object
    required: [ shots ]
    properties:
      shots:
        type: array
        min_items: 1
        items:
          type: object
          required: [ skill ]
          properties:
            skill:
              type: string
            windup:
              type: integer
              unit: point
              minimum: 0
            recovery:
              type: integer
              unit: point
              minimum: 0
            repeat:
              type: null

---

* **meta**
  - magic
    + 문서 형식 식별자
  - caster_key
    + 런타임 caster 태그의 접두사
  - values
    + stored 데이터가 저장된 항목
    + 불변 자료형 사용(생성 후 변경 불가, 중첩 요소도 동일)
* **kind**
  - stored는 기본 능력치의 magic_number를 기입하는 정적 항목
  - base는 능력치 변동 목록 stat의 최종 연산값을 나타내는 동적 항목
  - state는 stored와 base의 최종 연산값인 source를 나타내는 동적 항목
* **unit**
  - 모든 숫자는 **point (%p), percent (%)** 스타일로 표기
  - 모든 지속시간은 **1초 당 100%p**로 표기
* hp
  - 런타임 동적 항목
* **caster**
  - 시전자 태그 항목
  - 런타임에서 `caster_key#(고유ID)` 형식으로 발급
  - 문서에 직접 기입한 값은 런타임 테스트 전용 고정 태그
* **ratio**
  - source 적용 배율 수치 항목
  - stat 적용 배율 수치 항목
  - 음수 허용
* **tick**
  - 적용 간격 수치 항목
  - duration보다 적거나 같은 수치 적용
  - 타수와 무관한 단일 타격 안의 지속 효과 간격
* **factor**
  - tick 당 ratio 변동 수치 항목
* **apply**
  - holder
    + source를 불러올 target 항목
  - source
    + holder의 state 항목
  - fixed
    + change 무시 여부 항목
* stat
  - speed
    + movement_speed
    + attack_speed
  - projectile
    + projectile_aoe
    + projectile_range
    + projectile_speed
* **skills**
  - 스킬명을 키로 하는 스킬 목록 항목
  - 스킬명은 소문자 스네이크 케이스
  - 스킬 단위는 다단히트가 아닌 단일 타격
  - tags
    + skill 단위 속성 라벨
    + 동일 단위 parts 간 공유
  - parts
    + 단일 타격을 구성하는 use 객체 나열 목록
* **bursts**
  - 점사명을 키로 하는 점사 목록 항목
  - 점사명은 소문자 스네이크 케이스
  - shots
    + 점사를 구성하는 shot 나열 목록
    + 위에서 아래로 순서대로 진행
  - skill
    + 해당 shot에서 호출할 skills 항목명
    + skills에 없는 이름은 검증 실패
  - windup
    + shot 시작부터 타격이 들어가기까지의 지연 수치 항목
    + 생략 시 0
  - recovery
    + 타격 이후 다음 shot 시작까지의 지연 수치 항목
    + 생략 시 0, 마지막 shot은 점사 종료까지의 지연
  - repeat
    + 해당 burst 반복 항목
    + null

---

## concept

* null
* null
* null

---

## world-building

* null
* null
* null