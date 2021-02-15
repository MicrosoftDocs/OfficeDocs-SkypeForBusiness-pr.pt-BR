---
title: Perguntas frequentes (perguntas frequentes) sobre o Painel de Qualidade de Chamada (CQD)
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
description: Leia perguntas frequentes (perguntas frequentes) e respostas sobre o Painel de Qualidade de Chamada do Microsoft Teams (CQD).
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110254"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Perguntas frequentes (perguntas frequentes) sobre o Painel de Qualidade de Chamada (CQD)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

[Por que o CQD marca uma chamada como "Boa" se um ou mais participantes da reunião tiveram uma experiência ruim?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Por que vejo até 0,2% de diferença na chamada e na contagem de usuários em medidas e como obter volumes mais precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Por que os dados CQD do Skype for Business são diferentes dos dados CQD do Teams? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Por que não consigo ver EUII no CQD?](#why-cant-i-see-euii-in-cqd)

[Por que estou vendo informações do Skype for Business no CQD quando filtrei apenas o Teams?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Por que meus relatórios personalizados retornam no máximo 10.000 linhas quando sei que deve haver mais entradas?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Por que o CQD marca uma chamada como "Boa" se um ou mais participantes da reunião tiveram uma experiência ruim?

Confira as regras que o CQD usa para classificação [de fluxo.](stream-classification-in-call-quality-dashboard.md)
 
Para fluxos de áudio, qualquer um dos cinco classificadores, que são calculados para a média com base na duração da chamada, pode estar dentro de parâmetros "bons". Isso não significa que os usuários não experimentaram algo que contribuiu para uma queda de áudio, estática ou falha. 

Para determinar se foi um problema de rede, veja o delta entre os valores médios da sessão e os valores máximos. Os valores máximos são os máximos detectados e relatados durante a sessão.
 
Veja um exemplo de como solucionar essa situação. Digamos que você faça um rastreamento de rede durante uma chamada e os primeiros 20 minutos não haverá pacotes perdidos, mas então você terá uma lacuna de 1,5 segundos de pacotes e, em seguida, bom para o restante da chamada. A média será de <perda de pacotes de 10% (0,1) mesmo em uma análise de RTP de rastreamento do Wireshark. O que foi a Perda Máxima de Pacotes? 1,5 Segundos em um período de 5 segundos seria 30% (0,3). Isso ocorreu dentro do cinco segundo período de amostragem (talvez ou poderia ser dividido durante o período de amostragem)?
 
Se as métricas de rede parecem boas nas médias e valores máximos, procure outros dados de telemetria: 
- Verifique a taxa de evento insuficiente da CPU para ver se os recursos de CPU detectados disponíveis eram insuficientes e causavam baixa qualidade. 
- O dispositivo de áudio estava no modo Half Duplex para evitar comentários devido a microfones que estão próximos aos alto-falantes? 
- Verifique a Proporção de Eventos AEC Half Duplex do Dispositivo. O bug do dispositivo ou a falha do microfone introduziu ruído ou estático devido a saídas de áudio USB quando conectado a um Hub ou Estação de Encaixe:  
- Verifique as falhas do dispositivo e as taxas de eventos de falhas do microfone. O próprio dispositivo estava funcionando corretamente?  
- Verifique as taxas de evento capturar e renderizar o dispositivo que não está funcionando.


Para obter mais informações sobre dimensões e medidas disponíveis na telemetria CQD, leia Dimensões e medidas disponíveis no Painel de Qualidade [da Chamada.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Para ruído de fundo, verifique a taxa de evento mudo para ver o período em que os participantes ficaram com mudo mudo.
 
Crie relatórios detalhados no CQD e filtre na ID da Reunião para ver todos os usuários e fluxos em uma reunião e adicione os campos nos que você está interessado. Um usuário que está relatando o problema pode não ser o que estava tendo o problema. Eles estão apenas relatando a experiência.
 
A telemetria não necessariamente chamará a atenção para o problema, mas poderá ajudá-lo a entender melhor onde procurar e informar suas decisões. São atualizações de rede, dispositivo, driver ou firmware, uso ou usuário?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Por que vejo até 0,2% de diferença na chamada e na contagem de usuários em medidas e como obter volumes mais precisos? 
Para calcular as medidas de contagem de chamada e contagem de usuários, uma operação de contagem distinta é executada em relação aos identificadores de chamada ou usuário no conjunto de dados. Em grandes conjuntos de dados, há um erro de até 0,2% inerente à operação countif distinta. Para o volume mais preciso, você deve confiar nas medidas de contagem de fluxos, uma vez que elas não dependem dessa operação de contagem distinta. A filtragem para reduzir o volume de dados pode reduzir o erro, mas pode não eliminar essa fonte de erro em contagens distintas de chamada e usuários. Confira as [dimensões e medidas disponíveis](dimensions-and-measures-available-in-call-quality-dashboard.md) no Painel de Qualidade da Chamada para as quais as medidas são impactadas.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Por que os dados CQD do Skype for Business são diferentes dos dados CQD do Teams? 


> [!IMPORTANT]
> A partir de 1º de julho de 2020, o CQD (CQD.lync.com) mais antigo usa dados do CQD (CQD) mais recente. Teams.microsoft.com). Os dados mais antigos do CQD não estão mais disponíveis e você não pode exportar seus dados de criação ou relatório. Você ainda pode usar CQD.lync.com (disponível no Centro de administração do Skype for Business), mas desativaremos o acesso ao CQD.lync.com em breve, portanto, você deve mudar para o CQD. Teams.microsoft.com se você ainda não fez isso.


Se você estiver tentando comparar dados entre o CQD mais antigo do portal herdado do Skype for Business (cqd.lync.com) e o CQD mais recente do Centro de administração do Teams (cqd.teams.microsoft.com), perceberá rapidamente que os dados não corresponderão. Isso porque o CQD mais recente relata vários cenários de chamada adicionais. Se você ainda estiver usando relatórios do CQD mais antigo, use este artigo para ajudá-lo a interpretar esses relatórios: Painel de Qualidade de Chamada do [Skype for Business Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Por que não consigo ver EUII no CQD?

Essas funções de administrador podem acessar o CQD, mas não podem exibir EUII (informações de identificação do usuário final):
- Leitor de Relatórios do Microsoft 365
- Especialista em Suporte de Comunicações do Teams

Para saber mais sobre funções que podem acessar o CQD , incluindo EUII, leia Atribuir funções [para acessar o CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Por que estou vendo informações do Skype for Business no CQD quando filtrei apenas o Teams?

Quando você filtra apenas o Teams em relatórios CQD (isTeams = 1), você está filtrando todas as chamadas em que o *primeiro* ponto de extremidade é o Teams. Se o *segundo ponto de extremidade* for o Skype for Business, essas informações aparecerão no seu relatório CQD.

O CQDv2 e o CQDv3 sempre terão contagens totais diferentes, pois o CQDv3 terá novos cenários que o CQDv2 não terá. É por isso que a comparação de números de total de resumo ou agregados sem filtros terá essas diferenças esperadas.  

Dependendo do cenário de Clientes, o CQDv3 incluirá chamadas locais do SFB 2019 (se a SFB 2019 for usada com um conector de dados), chamadas do Bot do Skype (AA, CVI, VDI), Eventos Ao Vivo e chamadas PSTN. Cenários/recursos que estão disponíveis para os clientes, mas seus dados não estão no CQD V2.

Por exemplo, espera-se que seus clientes e você vejam 200.000 fluxos de áudio, com 5.000 falhas no Relatório de Resumo do CQD V2; versus 300.000 fluxos de áudio com 5.500 falhas (provenientes de chamadas no mesmo lugar de 2019, chamadas CVI, chamadas PSTN etc) no CQD V3.

Para determinar se há diferenças inesperadas, você deve verificar vários detalhamentos dos dados gerais.  Compare com intenção.  Cortar os dados por User Agent Category Pair é uma das primeiras coisas que recomendamos.  *First Product* and *Second Product também* são boas slicers.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Por que meus relatórios personalizados retornam no máximo 10.000 linhas quando sei que deve haver mais entradas?

O CQD foi projetado para consultas de dados resumidas e não foi projetado para exportação de dados. Recomendamos recomendá-los, sempre que possível, para impedir que o limite de 10.000 linhas seja excedido. Comece olhando para seus KPIs usando dimensões mais amplas e de menor cardinalidade, como Mês, Ano, Data, Região, País etc. A partir daí, você pode fazer uma drill down em dimensões cada vez mais altas de cardinalidade. Os Relatórios de Ajuda e Location-Enhanced fornecem bons exemplos desse fluxo de trabalho de drill down.

## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de Fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
