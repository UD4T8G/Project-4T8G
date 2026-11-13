---

magic: "UDOC/1"

caster_key: cursing_grandma

values:
  max_hp_default: 4T8G
  dps_default: 4T8G
  movement_speed_default: 4T8G
  attack_speed_default: 4T8G
  projectile_aoe_default: 4T8G
  projectile_range_default: 4T8G
  projectile_speed_default: 4T8G

skills:
  body:
    tags: []
    parts:
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: minimum
        factor: 4T8G
        apply: { holder: target, source: max_hp, fixed: true }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: minimum
        factor: 4T8G
        effect: { stat: movement_speed }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: minimum
        factor: 4T8G
        effect: { stat: attack_speed }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: minimum
        factor: 4T8G
        effect: { stat: projectile_aoe }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: minimum
        factor: 4T8G
        effect: { stat: projectile_range }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: minimum
        factor: 4T8G
        effect: { stat: projectile_speed }

bursts:
  body_slam:
    shots:
      - { skill: body, windup: 0, recovery: 0, repeat: null }

---

## concept

* ***욕쟁이 할머니 기획자는 UD이다.***
* 욕쟁이 할머니 기획 계기는 *원할머니 보쌈* 음식점에 대한 [빨랫방망이 할아버지](../../cabin-in-the-forest/batlet-grandpa/Batlet-Grandpa_Header.md) 기획자의 제안이었다.
  - 방문 당시 음식점 이름이 할머니 집인데 정작 아저씨들만 일하고 있었다.
  - 이후 아저씨들은 욕쟁이 할머니 기획자의 제안을 통해 [제임스 인페르노](../james-inferno/James-Inferno_Header.md)로 구현되었다.
* 욕쟁이 할머니 기획자의 제안을 통해 2026년에 *삼백집 이봉순 할머니* 설정이 구현되었다.
* 욕쟁이 할머니와 [빨랫방망이 할아버지](../../cabin-in-the-forest/batlet-grandpa/Batlet-Grandpa_Header.md) 간 우열 논쟁은 기획자 간 다툼으로 번지면서 결국 구상되지 않았다.

---

## world-building

* **[README](../../../../../README.md)**
  - [세계관 아키텍처](./Cursing-Grandma_Header.md#body)
* **삼백집 이봉순 할머니(박정희 대통령 방문 부정)**
  - [특징](./Cursing-Grandma_Main.md#characteristics)
* **삼백집 이봉순 할머니(어록)**
  - [대사집](./Cursing-Grandma_Main.md#lines)