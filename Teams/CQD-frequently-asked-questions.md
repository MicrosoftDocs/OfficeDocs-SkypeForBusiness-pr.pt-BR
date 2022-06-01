---
title: Perguntas frequentes sobre o CQD (Painel de Qualidade de Chamadas)
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Leia perguntas frequentes e respostas sobre o Microsoft Teams CQD (Painel de Qualidade de Chamadas).
ms.openlocfilehash: f320bab549ee322c1254babd0feb49cc24419215
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823200"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Perguntas frequentes sobre o CQD (Painel de Qualidade de Chamadas)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

[Por que o CQD marca uma chamada como "Boa" se um ou mais participantes da reunião tiveram uma experiência ruim?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Por que vejo até 0,2% de diferença nos valores de chamada e contagem de usuários em medidas e como obter volumes mais precisos? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Por que não consigo ver EUII no CQD?](#why-cant-i-see-euii-in-cqd)

[Estou tentando usar o CQD para relatórios de tipo de uso e descobrir que alguns dos dados estão incompletos. Por que isso?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Por que estou Skype for Business informações no CQD quando filtrei Teams dados?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Por que meus relatórios personalizados retornam apenas um máximo de 10.000 linhas quando sei que deve haver mais entradas?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Por que as Wi-Fi VPN são mostradas como com fio em vez de Wi-Fi?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Habilitamos a gravação baseada em políticas no Teams e agora as chamadas ponto a ponto estão sendo marcadas como Conferências. O que aconteceu?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Por que o CQD marca uma chamada como "Boa" se um ou mais participantes da reunião tiveram uma experiência ruim?

Confira as regras que o CQD usa para classificação [de fluxo](stream-classification-in-call-quality-dashboard.md).
 
Para fluxos de áudio, qualquer um dos cinco classificadores (que são calculados para a média com base no comprimento da chamada) pode estar dentro dos parâmetros "bons". Isso não significa que os usuários não experimentaram algo que contribuiu para uma queda de áudio, estática ou falha. 

Para determinar se foi um problema de rede, examine o delta entre os valores médios da sessão e os valores máximos. Os valores máximos são o máximo detectado e relatado durante a sessão.
 
Aqui está um exemplo de como solucionar essa situação. Digamos que você faça um rastreamento de rede durante uma chamada e, nos primeiros 20 minutos, não haja pacotes perdidos, mas, em seguida, você tem uma lacuna de 1,5 segundo de pacotes e, em seguida, é bom para o restante da chamada. A média será de <10% (0,1) Perda de pacote mesmo em uma análise de RTP de rastreamento do Wireshark. Qual foi a perda máxima de pacotes? 1,5 Segundo em um período de 5 segundos seria 30% (0,3). Isso ocorreu dentro do período de amostragem de 5 segundos (talvez ou pode ser dividido durante o período de amostragem)?
 
Se as métricas de rede parecem boas nas médias e nos valores máximos, procure outros dados de telemetria: 
- Verifique a taxa de eventos insuficiente da CPU para ver se os recursos de CPU detectados disponíveis eram insuficientes e causaram baixa qualidade. 
- O dispositivo de áudio estava no modo Half Duplex para evitar comentários devido a microfones muito próximos aos alto-falantes? 
- Verifique a taxa de eventos AEC do Dispositivo Half Duplex. Falha de um dispositivo, como um microfone, introduzindo ruído ou estático devido a saídas de áudio USB quando conectado a um Hub ou Estação de Encaixe?  
- Verifique as falhas de dispositivo e as taxas de eventos de falhas do microfone. O próprio dispositivo estava funcionando corretamente?  
- Verifique as taxas de eventos de captura e renderização do dispositivo que não está funcionando.


Para saber mais sobre dimensões e medidas disponíveis na telemetria do CQD, leia Dimensões e medidas disponíveis no [Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

Para ruído de fundo, verifique a taxa de eventos de mudo para ver o período em que os participantes foram mudos.
 
Crie relatórios detalhados no CQD e filtre a ID da Reunião para examinar todos os usuários e fluxos em uma reunião e adicionar os campos nos quais você está interessado. Um usuário que relata o problema pode não ser o que estava tendo o problema. Eles estão apenas relatando a experiência.
 
A telemetria não necessariamente chamará o problema, mas poderá ajudá-lo a entender melhor onde procurar e informar suas decisões. São atualizações de rede, dispositivo, driver ou firmware, uso ou usuário?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Por que vejo até 0,2% de diferença nos valores de chamada e contagem de usuários em medidas e como obter volumes mais precisos? 

Para calcular a contagem de chamadas e as medidas de contagem de usuários, uma operação countif distinta é executada em relação aos identificadores de chamada ou de usuário no conjunto de dados. Em grandes conjuntos de dados, há um erro de até 0,2% inerente à operação countif distinta. Para o volume mais preciso, você deve contar com medidas de contagem de fluxo, pois elas não dependem dessa operação countif distinta. A filtragem para reduzir o volume de dados pode reduzir o erro, mas pode não eliminar essa fonte de erro em chamadas distintas e contagens de usuário. Consulte [Dimensões e medidas disponíveis no Painel](dimensions-and-measures-available-in-call-quality-dashboard.md) de Qualidade de Chamadas para as quais as medidas são afetadas.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Por que não consigo ver EUII no CQD?

Essas funções de administrador podem acessar o CQD, mas não podem exibir EUII (informações de identificação do usuário final):

- Microsoft 365 leitor de relatórios
- Teams de Suporte de Comunicações

Para saber mais sobre as funções que podem acessar o CQD , incluindo EUII, leia Atribuir funções [para acessar o CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Estou tentando usar o CQD para relatórios de tipo de uso e descobrir que alguns dos dados estão incompletos. Por que isso?

Ferramentas de gerenciamento de qualidade de chamada, como CQD, Análise de Chamadas, CallRecord API do Graph e Análise em Tempo Real, são baseadas na telemetria de diagnóstico. As informações que mostramos em Teams de gerenciamento de qualidade de chamada são tão completas quanto os dados de telemetria que recebemos dos clientes que participam de uma chamada. Há vários motivos pelos quais podemos não receber telemetria completa, como interrupções de rede ou [configurações](/microsoft-365/enterprise/urls-and-ip-address-ranges) incorretas de firewall ou proxy. Estamos continuando a trabalhar para melhorar a confiabilidade e a resiliência com as quais os clientes Teams fornecem telemetria para o serviço.

Com isso em mente, não damos suporte ao uso de ferramentas de gerenciamento de qualidade de chamada para relatórios de uso. Eles não foram projetados para acomodar nem se destinam a esses tipos de cenários de relatório, e muitas estatísticas de uso não estão e não estarão disponíveis nessas ferramentas. Teams Administração Center oferece uma série de Relatórios de [Uso e um](teams-analytics-and-reports/teams-reporting-reference.md) Relatório de Participação [](teams-analytics-and-reports/meeting-attendance-report.md) na Reunião está disponível diretamente do Teams cliente.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Por que estou Skype for Business informações no CQD quando filtrei Teams dados?

Ao filtrar Teams somente em relatórios CQD (isTeams = 1), você está filtrando todas as chamadas em que o primeiro ponto de extremidade é  Teams. Se o *segundo ponto de extremidade* Skype for Business, essas informações aparecerão no relatório CQD. Dependendo dos cenários dos clientes, o CQD pode incluir Skype for Business Server 2019 quando o Conector de Dados [de](/skypeforbusiness/hybrid/plan-call-data-connector) Chamada estiver configurado. Ele também pode incluir chamadas Skype Bot (AA, CVI, VDI), Eventos ao Vivo e chamadas PSTN.

É possível remover informações Skype for Business de suas consultas filtrando dimensões como Primeira Categoria do Agente do Usuário e Segunda Categoria do  *Agente do Usuário*. Você também pode usar *o Par de Categorias* do Agente do Usuário que combina as dimensões Primeira e Segunda em um único filtro.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Por que meus relatórios personalizados retornam apenas um máximo de 10.000 linhas quando sei que deve haver mais entradas?

O CQD foi projetado para consultas de dados resumidas e não foi projetado para exportação de dados. É recomendável reestruturar seus relatórios, sempre que possível, para impedir que o limite de 10.000 linhas seja excedido. Comece examinando seus KPIs usando dimensões mais amplas e de cardinalidade mais baixa, como Mês, Ano, Data, Região, País e assim por diante. A partir daí, você pode fazer drill down em dimensões de cardinalidade cada vez mais altas. O Helpdesk e Location-Enhanced relatórios fornecem bons exemplos desse fluxo de trabalho de busca detalhada.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Por que as Wi-Fi VPN são mostradas como com fio em vez de Wi-Fi?

É esse o comportamento esperado. O fornecedor de VPN criou um adaptador Ethernet virtual que é tratado como uma conexão com fio. Como ele não está rotulado corretamente, o sistema operacional não sabe que é uma conexão Wi-Fi relata como com fio.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Habilitamos a gravação baseada em políticas no Teams e agora as chamadas ponto a ponto estão sendo marcadas como Conferências. O que aconteceu?

Esse é o comportamento esperado quando a gravação baseada em políticas está habilitada Microsoft Teams. A Gravação baseada em políticas usa um bot Teams Gravador implantado no Microsoft Azure para capturar o conteúdo da reunião para fins de conformidade. No gerenciamento de qualidade de chamadas, "ponto a ponto" é uma descrição do fluxo de tráfego de mídia, não da interação entre os usuários. Como um Bot do Gravador é uma parte da chamada, a chamada não é mais ponto a ponto, mas uma chamada de várias partes. Chamadas de várias partes são classificadas como Conferências por Microsoft Teams e, portanto, elas serão indicadas como tal quando você exibir essas chamadas no CQD e em outras ferramentas de qualidade de chamada.

## <a name="related-articles"></a>Artigos relacionados

[Melhorar e monitorar a qualidade da chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload locatário e criação de dados](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
