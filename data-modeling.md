# Sistema de Manutenção de Aeronaves

## 1. Descrição

Este projeto simula o registro de manutenções realizadas em aeronaves dentro de um hangar.

O objetivo é armazenar dados das manutenções e gerar métricas que permitam analisar o funcionamento das operações de manutenção.

---

## 2. Entidades

**aeronave**
Representa as aeronaves que passam por manutenção.

**tecnico**
Representa os técnicos responsáveis pelas manutenções.

**manutencao**
Representa as manutenções realizadas nas aeronaves.

**manutencao_tecnicos**
Tabela que registra quais técnicos participaram de cada manutenção.

---

## 3. Relacionamentos

* Uma aeronave pode ter várias manutenções (1:N)
* Um técnico pode participar de várias manutenções
* Uma manutenção pertence a uma aeronave
* Uma manutenção pode ter vários técnicos

A relação entre técnicos e manutenções é muitos-para-muitos (N:N), resolvida pela tabela `manutencao_tecnicos`.

---

## 4. Estrutura das tabelas

### aeronave

* id_aeronave (PK)
* registro
* modelo
* ano_fabricacao
* total_horas_voo

### tecnico

* id_tecnico (PK)
* nome
* especialidade
* nivel
* ano_contratacao

### manutencao

* id_manutencao (PK)
* id_aeronave (FK)
* tipo_manutencao
* status
* data_inicio
* data_fim

### manutencao_tecnicos

* id_manutencao (FK)
* id_tecnico (FK)
* funcao

---

## 5. Métricas que podem ser analisadas

* tempo de manutenção
* número de manutenções por técnico
* aeronaves com mais manutenções
* manutenções em andamento
* tempo médio de manutenção
