1. Descrição

Este projeto simula o processamento de dados de um hangar de manutenção de aeronaves.

O objetivo é registrar operações de manutenção e gerar métricas operacionais para analisar a eficiência dos processos de manutenção.
2. entidades
- aeronave
  representa os aviões em manutençãono hangar
- tecnico
  representa os responsaveis pelas manutenções
- manutenção
  representa as manutenções realizadas nas aeronaves
- manutencao_tecnicos
  tabela de relacionamento que registra quais técnicos participaram de cada manutenção e suas funções

3. relacionamentos
- uma aeronave pode ter diversas manutenções 1-n
- um tecico pode atuar em diversas manutenções 1-n
- uma manutenção pertence a uma aeronave (N:1)e ter um tecnico responsavel 1-1 mais os outros de outras certificações

4. justify modeling
- manutenção deve ter campo data_inicio e fim para medir o tempo do processo 
- manutenção deve ter campo responsáveis para observar desempenho de tecnicos
- total_horas_voo 

5. estrutura das tabelas
- aeronave
  id_aeronave PK
  registro
  modelo
  ano_fabricação
  total_horas_voo

- tecnico
  id_tecnico PK
  nome
  especialidade
  nivel
  ano_contratação
  
- manutenção
  id_manutenção PK
  id_aeronave FK
  tipo_manutenção
  status
  data_inicio
  data_fim

- manutencao_tecnicos
  id_manutencao FK
  id_tecnico FK
  funcao [responsavel, ajudante, pleno]
  
6. Métricas que o sistema deve permitir
- tempo de manutenção
- numero de manutenções por técnicos
- aeronaves com mais anutenções
- manutenções em andamento


    
