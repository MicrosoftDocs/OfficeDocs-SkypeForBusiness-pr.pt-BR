---
title: Perguntas frequentes (FAQ) sobre o painel de qualidade de chamada (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Leia perguntas frequentes (FAQ) e respostas sobre o Microsoft Teams Call Quality Dashboard (CQD).
ms.openlocfilehash: 8ad0a1745799194ec11284f8f7aaabd76bd30d05
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584020"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Perguntas frequentes (FAQ) sobre o painel de qualidade de chamada (CQD)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

[Por que o CQD marca uma chamada como "boa" se um ou mais participantes da reunião tivessem uma experiência ruim?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Por que vejo até 0,2% diferença de valores de contagem de usuários e chamada em medidas e como obter os volumes mais precisos?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Por que os dados do CQD do Skype for Business são diferentes dos dados do CQD do teams?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Por que não consigo ver o EUII no CQD?](#why-cant-i-see-euii-in-cqd)

[Por que estou vendo as informações do Skype for Business no CQD quando já filtro para o Microsoft Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Por que o CQD marca uma chamada como "boa" se um ou mais participantes da reunião tivessem uma experiência ruim?

Confira as regras que o CQD usa para [classificação de fluxo](stream-classification-in-call-quality-dashboard.md).
 
Para fluxos de áudio, qualquer um dos cinco classificadores, que são calculados para a média com base na duração da chamada, pode estar dentro dos parâmetros "bom". Não significa que os usuários não perceberam algo que contribuiu para um cancelamento de áudio, estático ou falha. 

Para determinar se foi um problema de rede, examine o Delta entre os valores médios da sessão e os valores máximos. O máximo de valores é o número máximo detectado e informado durante a sessão.
 
Veja um exemplo de como solucionar essa situação. Digamos que você tenha um rastreamento de rede durante uma chamada e os primeiros 20 minutos não há nenhum pacote perdido, mas você tem um intervalo de 1,5 segundos de pacotes e, em seguida, bom para o restante da chamada. A média será <10% (0,1) perda de pacotes mesmo em uma análise do Wireshark Trace RTP. Qual foi o máximo de perda de pacote? 1,5 segundos em um período de 5 segundos seria de 30% (0,3). Isso ocorreu dentro do período de amostragem de cinco segundos (talvez ou pode ser dividido no período de amostragem)?
 
Se as métricas de rede estiverem boas nos valores médias e máximos, procure outros dados de telemetria: 
- Verifique a taxa de eventos insuficientes da CPU para ver se os recursos de CPU detectados disponíveis eram insuficientes e causaram má qualidade. 
- O dispositivo de áudio está em modo Half duplex para evitar comentários devido aos microfones que estão prestes a ser fechados para os alto-falantes? 
- Verifique a taxa de evento de AEC duplex do dispositivo. O dispositivo está ocorrendo ou o microfone está apresentando ruído ou estático devido a esgotamentos de áudio USB quando conectado a um Hub ou uma docking Station:  
- Verifique as taxas de evento de falhas do dispositivo e do microfone. O próprio dispositivo está funcionando corretamente?  
- Verifique as taxas de eventos de captura e renderização que não estão funcionando.


Para saber mais sobre dimensões e medidas disponíveis na telemetria do CQD, consulte [dimensões e medidas disponíveis no painel de qualidade da chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).

Para ruído de fundo, marque a taxa de evento de mudo para ver a quantidade de tempo em que os participantes estavam em mudo.
 
Crie relatórios detalhados no CQD e filtre a ID da reunião para ver todos os usuários e fluxos em uma reunião e adicionar os campos dos quais você está interessado. Um usuário que informa que o problema pode não ser o que estava com o problema. Ele está apenas relatando a experiência.
 
A telemetria não irá necessariamente chamar o problema, mas pode ajudá-lo a entender melhor onde procurar e informar suas decisões. É uma rede, dispositivo, atualizações de driver ou firmware, uso ou usuário?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Por que vejo até 0,2% diferença de valores de contagem de usuários e chamada em medidas e como obter os volumes mais precisos? 
Para calcular a contagem de chamadas e os indicadores de contagem do usuário, uma operação cont.se diferente é realizada em relação à chamada ou aos identificadores de usuário no conjunto de dados. Em conjuntos de dados grandes, há um erro de até 0,2% inerente à operação cont.se distinta. Para o volume mais preciso, você deve confiar em medidas de contagem de fluxo, pois elas não dependem dessa operação cont.se distinta. A filtragem para reduzir o volume dos dados pode reduzir o erro, mas não pode eliminar essa fonte de erro em chamadas distintas e contagens de usuários. Consulte [dimensões e medidas disponíveis no painel de qualidade de chamada](dimensions-and-measures-available-in-call-quality-dashboard.md) para quais medidas são impactadas.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Por que os dados do CQD do Skype for Business são diferentes dos dados do CQD do teams? 


> [!IMPORTANT]
> A partir de 1 ° de julho de 2020, a CQD mais antiga (CQD.lync.com) usa os dados do CQD mais recente (CQD. Teams.microsoft.com). Os dados mais antigos do CQD não estão mais disponíveis, e você não pode exportar seus dados de construção ou relatório. Você ainda pode usar o CQD.lync.com (disponível no centro de administração do Skype for Business), mas desativaremos o acesso ao CQD.lync.com em breve, portanto, você deve se mover para o CQD. Teams.microsoft.com se ainda não fez isso.


Se você estiver tentando comparar dados entre o CQD antigo do portal herdado do Skype for Business (cqd.lync.com) e o CQD mais recente do centro de administração do Teams (cqd.teams.microsoft.com), perceberá rapidamente que os dados não são correspondentes. Isso é porque o mais recente CQD emite relatórios sobre muitos outros cenários de chamadas. Se você ainda estiver usando relatórios do CQD mais antigo, use este artigo para ajudá-lo a interpretar esses relatórios: [painel de qualidade de chamada para o Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Por que não consigo ver o EUII no CQD?

Essas funções de administrador podem acessar o CQD, mas não podem ver EUII (informações identificáveis pelo usuário final):
- Leitor de relatórios do Microsoft 365
- Especialista em suporte do teams Communications

Para saber mais sobre as funções que podem acessar o CQD-, incluindo EUII, [atribua funções para acessar o CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Por que estou vendo as informações do Skype for Business no CQD quando já filtro para o Microsoft Teams?

Ao filtrar para equipes somente nos relatórios do CQD (isteams = 1), você está filtrando todas as chamadas em que o *primeiro ponto de extremidade* é Teams. Se o *segundo ponto de extremidade* for o Skype for Business, essas informações serão exibidas no seu relatório do CQD.

CQDv2 e CQDv3 sempre terão contagens totais diferentes, pois CQDv3 terá novos cenários que o CQDv2 não terá. É por isso que comparar números totais de resumo ou de todos os números agregados sem filtros terá essas diferenças esperadas.  

Dependendo do cenário do cliente, o CQDv3 incluirá as chamadas locais do SFB 2019 (se SFB 2019 for usado com um conector de dados), as chamadas do Skype bot (AA, CVI, VDI), eventos dinâmicos e chamadas PSTN. Cenários/recursos que estão disponíveis para os clientes, mas seus dados não estão no CQD v2.

Por exemplo, espera-se que seus clientes vejam os fluxos de áudio do 200.000 com falhas do 5000 no relatório de resumo do CQD v2; versus fluxos de áudio do 300.000 com falhas do 5500 (provenientes de 2019 chamadas locais, chamadas CVI, chamadas PSTN etc) no CQD v3.

Para determinar se há diferenças inesperadas, você deve observar várias divisões dos dados gerais.  Comparar com objetivo.  A divisão dos dados pelo par de categorias de agente do usuário é uma das primeiras coisas que recomendamos.  O *primeiro produto* e o *segundo produto* também são bons slicers.  


## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o painel de qualidade da chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados do locatário e construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)