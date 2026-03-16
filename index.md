[🇧🇷 Português](./) | [🇺🇸 English](index-en.md)

# Aplicação de modelos de reconhecimento de ações em vídeos para o problema de monitoramento de idosos

Este projeto investiga o uso de modelos de **Visão Computacional** para o monitoramento não invasivo de idosos, focando na identificação de **Atividades de Vida Diária (AVDs)** e situações de risco sem a necessidade de sensores vestíveis.

## 🎯 Objetivos

O objetivo geral foi aplicar e avaliar um modelo de reconhecimento de ações que utiliza exclusivamente entradas de vídeo para identificar atividades cotidianas de forma precisa e eficiente.

- **Identificação de Ações:** Detectar eventos relevantes e comportamentos atípicos.
- **Preservação da Autonomia:** Propor uma solução não intrusiva que dispense dispositivos acoplados ao corpo.
- **Eficiência Computacional:** Avaliar o desempenho em termos de acurácia e custo de processamento.

## 📊 Dataset

Foi utilizado o conjunto de dados [**Toyota Smarthome Trimmed (TST)**](https://project.inria.fr/toyotasmarthome/).

**Características:**  
Composto por vídeos de idosos realizando atividades em ambientes domésticos reais.

**Granularidade:**  
Originalmente possui **31 classes de ações** com alta variabilidade postural.

**Protocolo:**  
Seguiu o protocolo **Cross-Subject** para avaliar a generalização do modelo para diferentes indivíduos.

## 🛠️ Métodos

A metodologia baseou-se no framework **PoseConv3D**, que foca na representação da pose humana.

**Estimativa de Pose:**  
Extração de pontos-chave (articulações) das imagens para gerar **mapas de calor 2D ao longo do tempo**.

**Arquitetura 3D-CNN:**  
Uso da rede **X3D** para processar esses mapas de calor, capturando padrões espaciais e temporais das ações.

**Agrupamento Semântico:**  
Agrupamento Semântico: Redução das 31 classes originais para 19 classes. Ações similares que variavam apenas pelo objeto (ex: beber de copo vs. beber de garrafa) foram unificadas para melhorar o aprendizado de padrões motores fundamentais.

## 📈 Resultados

O model demonstrou desempenho superior a método original baseado apenas em pose desenvolvido para o TST em termos de **acurácia média por classe** .

### Dataset Completo (31 classes)

- **Acurácia Global:** 72,2%
- **Acurácia Média por Classe:** 54,5%

### Dataset Agrupado (19 classes)

- **Acurácia Global:** 77,7%
- **Acurácia Média por Classe:** 67,9%

**Eficiência:**  
O treinamento do conjunto completo levou cerca de **12 horas em uma única GPU**, sendo mais eficiente que abordagens que combinam múltiplas fontes de entrada (como **RGB + Pose**).

## 🚀 Trabalhos Futuros
1. **Monitorização em Tempo Real**: Desenvolvimento de uma infraestrutura que permita o envio de alertas imediatos em caso de quedas ou comportamentos de risco.
2. **Agrupamento por Postura**: Explorar estratégias de agrupamento baseadas na similaridade das poses corporais (ex: ações realizadas sentado vs. em pé) para reduzir confusões do modelo.
3. **Privacidade e Edge Computing**: Implementar o sistema em dispositivos de baixo custo para processamento local, garantindo que os dados de vídeo não saiam da residência do idoso.
## 💻 Tecnologias utilizadas

- PyTorch
- [PySKL](https://github.com/kennymckormick/pyskl)
- MMCV
- HRNet
- OpenCV
- Python
- CUDA (GPU)

## 🔬 Técnicas e áreas

- Reconhecimento de Ações Humanas
- Visão Computacional
- Aprendizado Profundo
- Redes Neurais Convolucionais 3D
- Estimativa de Pose Humana (Mapas de calor)

## 📄 Autor

**Beatriz Aparecida Benedicto Heleno**  
Mestranda em Ciência da Computação — Universidade Federal de Juiz de Fora (UFJF)  
Área de pesquisa: Visão Computacional e Computação Gráfica

📄 Monografia (TCC):  
[Aplicação de modelos de reconhecimento de ações em vídeos para o problema de monitoramento de idosos](http://monografias.ice.ufjf.br/tcc-web/tcc?id=1077)

🎥 **Vídeo de apresentação (SEMIC 2025):**  
[Assista à apresentação do projeto](https://www.youtube.com/watch?v=alc41NiFxrg)

🔗 LinkedIn:  
https://linkedin.com/in/beatrizbenedicto
