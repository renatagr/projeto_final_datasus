# Nanodegree Engenheiro de Machine Learning

Projeto Final: Avaliação de modelos de predição de pacientes de alto custo no Sistema Único de Saúde.
Base de dados: Datasus
Período de avaliação: Janeiro de 2016 a Dezembro de 2017
Objetivo final: Estimativas indicam que 10% dos pacientes portadores de doenças crônicas representam 2/3 dos custos totais com saúde no Brasil. Desta forma, o objetivo deste projeto será predizer com acurácia quais indivíduos possuem maior risco de ser um paciente de alto custo (H_COST). 

### Instalação

Este projeto requer **Python 3.6.4** e as seguintes bibliotecas Python instaladas:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org/)
- [Matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)
- Seaborn
 

### Código

Também será necessário usar:
- arquivo Python `visuals.py` 
- Arquivo de dados `BASE_DADOS_FINAL4.csv` (em função do tamanho, será disponibilizado no onedrive:
https://1drv.ms/f/s!ArJP0W5PAIXbg7Il3t-Slr23-rem4g




### Dados

**Atributos**
UF: discreto. Codigo UF 11 Rondônia 12 Acre 13 Amazonas 14 Roraima 15 Pará 16 Amapá 17 Tocantins 21 Maranhão 22 Piauí 23 Ceará 24 Rio Grande do Norte 25 Paraíba 26 Pernambuco 27 Alagoas 28 Sergipe 29 Bahia 31 Minas Gerais 32 Espírito Santo 33 Rio de Janeiro 35 São Paulo 41 Paraná 42 Santa Catarina 43 Rio Grande do Sul 50 Mato Grosso do Sul 51 Mato Grosso 52 Goiás 53 Distrito Federal 0 Ignorado/exterior
SEXO: discreto. 
1 - Masculino, 
3 - Feminino.
QT_DIARIAS: contínuo Quantidade de dias de internação de cada paciente (total de dias de internação do paciente nos anos de 2016 e 2017)
VAL_SH:contínuo. Valor de serviços hospitalares
VAL_SP:contínuo. Valor de serviços profissionais
VAL_SADT:contínuo. Valor de SADT (serviços auxiliares de diagnose e terapia)
VAL_RN:contínuo. Valor de recém-nato
VAL_ACOMP:contínuo. Valor de diárias de acompanhante
VAL_ORTP:contínuo. Valor de órtese e prótese
VAL_SANGUE:contínuo. Valor de sangue
VAL_SADTSR:contínuo. Valor referente a tomografias e ressonância nuclear magnética pagas diretamente a terceiros, sem rateio. Observação: este valor está somado em VAL_TOT, mas não em VAL_SADT.
VAL_TRANSP:contínuo. Valor referente a transplantes (retirada de órgãos), incluindo: - taxa de sala cirúrgica (SH) - retirada de órgão (SP) - exames no cadáver (SADT) - avaliação auditiva (SADT) - exames dos transplantados (SADT) Observação: este valor está somado em VAL_TOT, mas não em VAL_SH, VAL_SP e VAL_SADT.
VAL_OBSANG:contínuo. Valor de analgesia obstétrica
VAL_PED1AC:contínuo. Valor de pediatria - primeira consulta
VAL_UTI:contínuo. Valor referente aos gastos em UTI
MORTE: discreto. Indica se o paciente teve saída com morte: 0: Não 1: Sim (Nesta base de dados, já foram excluídos os registros de pacientes mortos.
INSTRU:discreto. Grau de instrução
Ignorado/não se aplica: 0
Analfabeto: 1
1º grau: 2
2º grau: 3
3º grau: 4
IDADE: contínuo.
RACA_COR:discreto 
Sem informação 99
Branca 1
Preta 2
Parda 3
Amarela 4
Indígena 5
INSTRU: discreto. Nível de instrução do paciente
Ignorado/não se aplica 0
Analfabeto 1
1º grau 2
2º grau 3
3º grau 4
VAL_TOT: contínuo Valor total em despesas médicas para cada paciente entre os anos de 2016 e 2017. Equivale ao seguinte cálculo: Valor total da AIH (Variável Val_Tot)= VAL_SH + VAL_SP + VAL_SADT + VAL_RN + VAL_ACOMP + VAL_ORTP + VAL_SANGUE + VAL_SADTSR + VAL_TRANSP + VAL_OBSANG + VAL_PED1AC
BODY_SYSTEM: discreto. Agrupamento de doenças conforme o código relacionado ao campo DIAG_PRINC Diagnóstico principal, segundo a CID. BODY_SYSTEM Descrição - Grupo de Doenças 1 Algumas doenças infecciosas e parasitárias 2 Neoplasias [tumores] 3 Doenças endócrinas, nutricionais e metabólicas 4 Doenças do sangue e dos órgãos hematopoéticos e alguns transtornos imunitários 5 Transtornos mentais e comportamentais 6 Doenças do sistema nervoso 7 Doenças do aparelho circulatório 8 Doenças do aparelho respiratório 9 Doenças do aparelho digestivo 10 Doenças do aparelho geniturinário 11 Gravidez, parto e puerpério 12 Doenças da pele e do tecido subcutâneo 13 Doenças do sistema osteomuscular e do tecido conjuntivo 14 Malformações congênitas, deformidades e anomalias cromossômicas 15 Algumas afecções originadas no período perinatal 16 Sintomas, sinais e achados anormais de exames clínicos e de laboratório, não classificados em outra parte 17 Lesões, envenenamento e algumas outras consequências de causas externas 18 Fatores que influenciam o estado de saúde e o contato com os serviços de saúde

**Variável-alvo**
- H_COST: DISCRETO.
1 - se paciente teve custos médicos superiores ao percentil de 95%
0 - se paciente teve custos médicos até o percentil de 95%.
