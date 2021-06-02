---
title: Painel de Qualidade de Chamada (CQD) Perguntas frequentes (perguntas frequentes)
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
description: Leia perguntas frequentes (perguntas frequentes) e respostas sobre Microsoft Teams Painel de Qualidade de Chamada (CQD).
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718002"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Painel de Qualidade de Chamada (CQD) Perguntas frequentes (perguntas frequentes)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

[Por que o CQD marca uma chamada como "Boa" se um ou mais participantes da reunião tiveram uma experiência ruim?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Por que vejo até 0,2% de diferença nos valores de chamada e contagem de usuários em medidas e como obter volumes mais precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Por que os dados do CQD Skype for Business diferentes dos dados CQD do Teams?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Por que não consigo ver EUII no CQD?](#why-cant-i-see-euii-in-cqd)

[Por que estou vendo Skype for Business informações no CQD quando filtrei Teams apenas?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Por que meus relatórios personalizados só retornam no máximo 10.000 linhas quando eu sei que deve haver mais entradas?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Por que as conexões VPN WiFi mostram como Wired em vez de WiFi?](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Por que o CQD marca uma chamada como "Boa" se um ou mais participantes da reunião tiveram uma experiência ruim?

Confira as regras que o CQD usa para classificação [de fluxo.](stream-classification-in-call-quality-dashboard.md)
 
Para fluxos de áudio, qualquer um dos cinco classificadores, que são calculados para a média com base no comprimento da chamada, pode estar todos dentro de parâmetros "bons". Isso não significa que os usuários não experimentaram algo que contribuiu para uma saída de áudio, estática ou falha. 

Para determinar se foi um problema de rede, veja o delta entre os valores médios da sessão e os valores máximos. Os valores máximos são os máximos detectados e relatados durante a sessão.
 
Veja um exemplo de como solucionar essa situação. Digamos que você faça um rastreamento de rede durante uma chamada e nos primeiros 20 minutos não há pacotes perdidos, mas, em seguida, você tem um intervalo de 1,5 segundos de pacotes e, em seguida, bom para o restante da chamada. A média será de <perda de pacotes de 10% (0,1) mesmo em uma análise RTP de rastreamento de Wireshark. O que foi a Perda de Pacotes Max? 1,5 Segundos em um período de 5 segundos seriam 30% (0,3). Isso ocorreu dentro do período de amostragem de 5 segundos (talvez ou pode ser dividido durante o período de amostragem)?
 
Se as métricas de rede parecem boas nas médias e nos valores máximos, procure outros dados de telemetria: 
- Verifique a Taxa de Eventos Insuficientes da CPU para ver se os recursos de CPU detectados disponíveis eram insuficientes e causavam má qualidade. 
- O dispositivo de áudio estava no modo Half Duplex para evitar comentários devido a microfones que devem ser próximos aos alto-falantes? 
- Verifique a taxa de eventos AEC de Dispositivo SemiDuplex. O dispositivo falhou ou a falha do microfone introduziu ruído ou estática devido a Saídas de Áudio USB quando conectado a um Hub ou Docking Station?  
- Verifique as taxas de eventos Buges de Dispositivo e Falhas de Microfone. O próprio dispositivo estava funcionando corretamente?  
- Verifique as taxas de eventos Captura e Renderização do Dispositivo Não Funcionando.


Para obter mais informações sobre dimensões e medidas disponíveis na telemetria do CQD, leia Dimensões e medidas disponíveis no Painel de Qualidade [de Chamada.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Para ruído em segundo plano, verifique a taxa de eventos mute para ver o tempo em que os participantes foram silenciados.
 
Crie relatórios detalhados no CQD e filtre a ID da Reunião para ver todos os usuários e fluxos em uma reunião e adicionar os campos nos que você está interessado. Um usuário que relata o problema pode não ser o que estava tendo o problema. Eles estão apenas relatando a experiência.
 
A telemetria não chamará necessariamente o problema, mas poderá ajudá-lo a entender melhor onde procurar e informar suas decisões. São atualizações de rede, dispositivo, driver ou firmware, uso ou usuário?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Por que vejo até 0,2% de diferença nos valores de chamada e contagem de usuários em medidas e como obter volumes mais precisos? 
Para calcular a contagem de chamada e as medidas de contagem de usuários, uma operação countif distinta é executada em relação à chamada ou aos identificadores do usuário no conjunto de dados. Em conjuntos de dados grandes, há um erro de até 0,2% inerente à operação countif distinta. Para o volume mais preciso, você deve depender das medidas de contagem de fluxo, pois elas não dependem dessa operação countif distinta. A filtragem para reduzir o volume de dados pode reduzir o erro, mas pode não eliminar essa fonte de erro em contagens distintas de chamada e de usuário. Consulte [Dimensões e medidas disponíveis no Painel](dimensions-and-measures-available-in-call-quality-dashboard.md) de Qualidade de Chamada para as quais as medidas são impactadas.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Por que os dados do CQD Skype for Business diferentes dos dados CQD do Teams? 


> [!IMPORTANT]
> A partir de 1º de julho de 2020, o CQD mais antigo (CQD.lync.com) usa dados do CQD mais recente (CQD.Teams.microsoft.com). Os dados CQD mais antigos não estão mais disponíveis e você não pode exportar seus dados de construção ou relatório. Você ainda pode usar CQD.lync.com (disponível no centro de administração do Skype for Business), mas desativaremos o acesso ao CQD.lync.com em breve, portanto, você deve mudar para o CQD. Teams.microsoft.com se você ainda não fez isso.


Se você estiver tentando comparar dados entre o CQD mais antigo do portal herdado do Skype for Business (cqd.lync.com) e o CQD mais recente do centro de administração do Teams (cqd.teams.microsoft.com), você notará rapidamente que os dados não são comparados. Isso porque os relatórios mais recentes do CQD sobre muitos cenários de chamada adicionais. Se você ainda estiver usando relatórios do CQD mais antigo, use este artigo para ajudá-lo a interpretar esses relatórios: [Painel](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)de Qualidade de Chamada para Skype for Business Server .


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Por que não consigo ver EUII no CQD?

Essas funções de administrador podem acessar o CQD, mas não podem exibir EUII (informações de identificação do usuário final):
- Microsoft 365 Leitor de relatórios
- Teams Especialista em Suporte de Comunicações

Para saber mais sobre funções que podem acessar o CQD - incluindo EUII - leia [Atribuir funções para acessar CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Por que estou vendo Skype for Business informações no CQD quando filtrei Teams apenas?

Quando você filtra para Teams somente em relatórios CQD (isTeams = 1),  você está filtrando todas as chamadas em que o primeiro ponto de extremidade é Teams. Se o *segundo ponto de extremidade* Skype for Business, essas informações aparecerão no relatório do CQD.

O CQDv2 e o CQDv3 sempre terão contagens totais diferentes, pois o CQDv3 terá novos cenários que o CQDv2 não terá. É por isso que a comparação de números de resumo total ou all-up agregados sem filtros terá essas diferenças esperadas.  

Dependendo do cenário dos clientes, o CQDv3 incluirá chamadas locais do SFB 2019 (se o SFB 2019 for usado com um conector de dados), chamadas de bot Skype (AA, CVI, VDI), Eventos Ao Vivo e chamadas PSTN. Cenários/recursos que estão disponíveis para os clientes, mas seus dados não estão no CQD V2.

Por exemplo, é esperado que seus clientes e você vejam 200.000 fluxos de áudio, com 5.000 falhas no Relatório de Resumo do CQD V2; versus 300.000 fluxos de áudio com 5500 falhas (provenientes de chamadas 2019 on-prem, chamadas CVI, chamadas PSTN etc.) no CQD V3.

Para determinar se há diferenças inesperadas, você deve verificar várias repartições dos dados gerais.  Compare com intenção.  Cortar os dados pelo User Agent Category Pair é uma das primeiras coisas que recomendamos.  *O Primeiro Produto* *e o Segundo Produto* também são bons cortadores de dados.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Por que meus relatórios personalizados só retornam no máximo 10.000 linhas quando eu sei que deve haver mais entradas?

O CQD foi projetado para consultas de dados resumidas e não foi projetado para exportação de dados. Recomendamos a reestruturação de seus relatórios, sempre que possível, para evitar que o limite de 10.000 linhas seja excedido. Comece olhando seus KPIs usando dimensões mais amplas e de menor cardinalidade, como Mês, Ano, Data, Região, País, etc. A partir daí, você pode detalhar as dimensões cada vez mais elevadas. O Helpdesk e Location-Enhanced relatórios fornecem bons exemplos desse fluxo de trabalho de detalhamento.

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a>Por que as conexões VPN WiFi mostram como Wired em vez de WiFi?

Isso é esperado. O fornecedor vpn criou um adaptador ethernet virtual que é tratado como uma conexão com fio. Como não está rotulado corretamente, o sistema operacional não sabe que é uma conexão WiFi e a relata como com fio.

## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload locatário e a criação de dados](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade de chamada e reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
