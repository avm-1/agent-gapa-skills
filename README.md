# Agent GAPA Skills

<p align="center">
  <b>G</b>eneral <b>A</b>gent <b>P</b>erformance & <b>A</b>daptation
</p>

<p align="center">
  <a href="#русский">🇷🇺</a> • <a href="#english">🇬🇧</a>
</p>

---

<a name="русский"></a>
## 🇷🇺

**Agent GAPA Skills** — это набор самообучающихся агентских навыков, направленных на итеративное улучшение работы ИИ-агентов, запоминание ошибок и их предотвращение при работе с кодом и инфраструктурой.

### Быстрый старт

```bash
git clone https://github.com/avm-1/agent-gapa-skills.git
cd agent-gapa-skills
```

### Философия

> Каждая ошибка — это данные. Каждый успех — это алгоритм.

Агенты не должны забывать свой опыт. Этот проект создаёт систему, в которой агенты:
- Анализируют свои действия после каждой задачи
- Извлекают успешные паттерны и оформляют их как переиспользуемые навыки
- Запоминают ошибки как антипаттерны, чтобы не повторять их

### Структура проекта

```
.agents/skills/
└── gapa-self-learning/          # Навык рефлексии и самообучения
    ├── SKILL.md                 # Инструкция для агента
    └── references/
        ├── reflection-template.md   # Шаблон анализа логов
        └── anti-pattern-log.md      # Лог ошибок
MEMORY.md                        # Глобальная память проекта
AGENTS.md                        # Конвенции для агентов
```

### Как это работает

1. **Триггеры рефлексии**: завершение таска, 10+ вызовов инструментов, сложный баг или ошибка
2. **Анализ**: агент отвечает на вопросы шаблона рефлексии
3. **Извлечение**: успешные алгоритмы записываются как skills, ошибки — как антипаттерны
4. **Переиспользование**: в будущем агент применяет накопленные знания автоматически

### Навыки

| Навык | Описание |
|-------|----------|
| `gapa-self-learning` | Рефлексия, извлечение алгоритмов, запись антипаттернов |

### Эксперимент: ловушка на коде 1С

Мы провели стресс-тест: один и тот же модуль 1С с 5 намеренно внесёнными багами анализировали два агента — с навыками (`plan-validator` + `tool-enforcer`) и без.

**Результат**: агент с навыками нашёл **10 проблем**, агент без — **7** (+43%).  
При этом агент с навыками выявил глубинные архитектурные риски (race condition, UX-ловушки, граничные условия), которые агент без навыков пропустил.

Подробный отчёт: [`experiment/1c-trap/REPORT.md`](experiment/1c-trap/REPORT.md)

### Контрибуция

Проект открыт для экспериментов. Если у тебя есть идея для нового skill или улучшения системы рефлексии — welcome!

---

<a name="english"></a>
## 🇬🇧

**Agent GAPA Skills** is a collection of self-learning agent skills focused on iterative improvement of AI agents, remembering mistakes, and preventing them when working with code and infrastructure.

### Quick Start

```bash
git clone https://github.com/avm-1/agent-gapa-skills.git
cd agent-gapa-skills
```

### Philosophy

> Every failure is data. Every success is an algorithm.

Agents shouldn't forget their experience. This project creates a system where agents:
- Analyze their actions after each task
- Extract successful patterns and package them as reusable skills
- Remember failures as anti-patterns to avoid repetition

### Project Structure

```
.agents/skills/
└── gapa-self-learning/          # Reflection and self-learning skill
    ├── SKILL.md                 # Agent instruction
    └── references/
        ├── reflection-template.md   # Log analysis template
        └── anti-pattern-log.md      # Failure log
MEMORY.md                        # Global project memory
AGENTS.md                        # Agent conventions
```

### How It Works

1. **Reflection triggers**: task completion, 10+ tool calls, complex bug or error
2. **Analysis**: agent answers reflection template questions
3. **Extraction**: successful algorithms are recorded as skills, failures as anti-patterns
4. **Reuse**: in the future, the agent automatically applies accumulated knowledge

### Skills

| Skill | Description |
|-------|-------------|
| `gapa-self-learning` | Reflection, algorithm extraction, anti-pattern logging |

### Experiment: 1C Code Trap

We ran a stress test: two agents analyzed the same 1C module with 5 intentional bugs — one with skills (`plan-validator` + `tool-enforcer`), one without.

**Result**: the agent with skills found **10 issues**, the agent without — **7** (+43%).  
The skilled agent also uncovered deep architectural risks (race conditions, UX traps, edge cases) that the unskilled agent missed.

Full report: [`experiment/1c-trap/REPORT.md`](experiment/1c-trap/REPORT.md)

### Contributing

This project is open for experiments. If you have an idea for a new skill or improving the reflection system — welcome!

---

<p align="center">
  Built for agents who never stop learning.
</p>
