Adão Yuri Ferreira da Silva, RM: 559223

João Vitor Lopes Santana, RM: 560781

Link Youtube: https://www.youtube.com/watch?v=e_VFizqYYKI

ou

https://youtu.be/e_VFizqYYKI

# WorkSafe -- Plataforma de Monitoramento Ergonômico e Saúde Ocupacional

O WorkSafe é uma plataforma digital integrada para monitoramento e
promoção de ergonomia, saúde ocupacional e bem-estar em ambientes de
trabalho remotos, híbridos e presenciais. A solução combina backend em
Spring Boot, PostgreSQL, Node-RED e tecnologias IoT.

## 1. Descrição do Projeto

O WorkSafe foi projetado para ajudar empresas a monitorar riscos
ergonômicos, condições de trabalho e apoiar colaboradores através de
dados objetivos e recomendações.

## 2. Problema e Motivação

Colaboradores com TDAH, TEA, ansiedade, dislexia e PCD enfrentam
sobrecarga sensorial, falta de foco, ergonomia inadequada e cansaço
mental. O WorkSafe propõe uma solução inclusiva, acessível e
inteligente.

## 3. Público-Alvo

-   Pessoas com TDAH, TEA, ansiedade e dislexia\
-   PCDs (visual/auditiva)\
-   Equipes remotas, híbridas e presenciais\
-   RH, SST, TI e Compliance

## 4. Arquitetura da Solução

1.  **Dispositivo IoT** envia JSON com temperatura, umidade, luz, ruído
    e postura.\
2.  **Node-RED** processa e classifica o status.\
3.  **Dashboard** exibe status geral, gauge de luminosidade e gráfico de
    temperatura.

### JSON do sensor:

    {
      "temperature": 25.3,
      "humidity": 50,
      "light": 380,
      "noise": 650,
      "posture": "ok"
    }

### Lógica de Classificação (Node-RED)

    let d = msg.payload;
    let status = "OK";

    if (d.posture === "bad") status = "Postura inadequada";
    else if (d.light < 200) status = "Luz insuficiente";
    else if (d.noise > 900) status = "Ruído elevado";
    else if (d.temperature > 30) status = "Temperatura alta";

    msg.payload.status = status;
    return msg;

### PRINTS NECESSÁRIOS, CONFERIR NO PDF DA ENTREGA
