---
title: Relatório de uso PSTN do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Saiba como usar o relatório de uso de PSTN do teams no centro de administração do Microsoft Teams para obter uma visão geral do uso de chamadas e videoconferências em sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89d33f15401d25767c905f16e38d93744d7929c3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570562"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Relatório de uso PSTN do Microsoft Teams

O relatório de uso de PSTN do teams no centro de administração do Microsoft Teams oferece uma visão geral de atividades de chamadas e conferência de áudio em sua organização. Você pode exibir atividades de chamada detalhadas para planos de chamada se usar a Microsoft como sua operadora de telefonia e para roteamento direto se você usar sua própria operadora de telefonia.

A guia **planos de chamada** mostra informações, incluindo o número de minutos gastos pelos usuários em chamadas PSTN de entrada e saída e o custo dessas chamadas. A guia **encaminhamento direto** mostra informações incluindo o endereço SIP e os horários de início e término da chamada. Use as informações neste relatório para obter informações sobre o uso da PSTN em sua organização e ajudá-lo a investigar, planejar e tomar decisões de negócios.

## <a name="view-the-report"></a>Exibir o relatório

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** > relatórios de**uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **relatório de uso de PSTN**.
2. Em **intervalo de datas**, selecione um intervalo predefinido de 7 ou 28 dias, ou defina um intervalo personalizado e selecione **executar relatório**.

## <a name="interpret-the-report"></a>Interpretar relatório

### <a name="calling-plans"></a>Planos de Chamadas

![Captura de tela do relatório de relatório de uso PSTN dos planos de chamada no centro de administração](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Captura de tela do relatório de uso de PSTN no centro de administração do Microsoft Teams com textos explicativos numerados")

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser exibido para obter tendências nos últimos sete dias, 28 dias ou um intervalo de datas personalizado que você definiu |
|**2**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período de tempo selecionado. <br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela oferece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora de início da chamada.</li><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams.</li><li>**Nome** de usuário é o nome do usuário.</li><li>**Número de telefone** é o número que recebeu a chamada para chamadas recebidas ou o número discado para chamadas feitas.</li><li>**Tipo de chamada** é se a chamada foi uma chamada PSTN de saída ou de entrada e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que podem ser exibidas incluem:<br><br>**Tipos de chamada de usuário do teams**<ul><li>**user_in** -o usuário recebeu uma chamada PSTN de entrada.</li><li>**user_out** -o usuário fez uma chamada PSTN de saída</li><li>**user_out_conf** -o usuário adicionou dois ou mais participantes PSTN à chamada, como uma chamada em conferência tripla</li><li>**user_out_transfer** -o usuário transferiu a chamada para um número PSTN</li><li>**user_out_forwarding** -o usuário encaminhou a chamada para um número PSTN</li><li>**conf_in** -uma chamada de entrada para a ponte de audioconferência</li><li>**conf_out** -uma chamada de saída da ponte de videoconferência geralmente para adicionar um número PSTN à conferência</li></ul><br>**Tipos de chamada de bots do teams**<ul><li>**ucap_in** -uma chamada PSTN de entrada para o Teams bot, como atendedor automático ou fila de chamadas</li><li>**ucap_out** -uma chamada PSTN de saída de um bot de equipe, como atendedor automático ou fila de chamadas</li></ul><br><li>**Chamado para** é o número discado.</li><li>**Para país ou região** , a discagem do país ou região.</li><li>**Chamado de** é o número que fez a chamada.</li><li>**Do país ou região** é o país ou região de onde a chamada foi feita.</li><li>**Encargo** é a quantia de dinheiro ou o custo da chamada cobrada na sua conta. </li><li>**Moeda** é o tipo de moeda usado para calcular o custo da chamada. </li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Doméstica/internacional** informa se a chamada foi doméstica (dentro de um país ou região) ou internacional (fora de um país ou região) com base na localização do usuário.</li><li>A **ID da chamada** é a ID da chamada para uma chamada. Trata-se de um identificador exclusivo para a chamada que você pode usar ao ligar para o suporte da Microsoft.</li><li>**Tipo de número** é o tipo de número de telefone do usuário, como um serviço de número de chamada gratuita. </li><li>**País ou região** é o local de uso. </li> <li>**ID de conferência** é a ID de conferência da conferência de áudio. </li><li>**Recurso** é a licença usada para a chamada. Os tipos de licença que podem ser exibidos incluem:<ul><li>**MCOPSTNPP** -créditos de comunicações</li><li>**MCOPSTN1** -plano de chamadas domésticas (3000 min-US/1200 min) planos da UE)</li><li>**MCOPSTN2** -plano de chamadas internacionais</li><li>**MCOPSTN5** -plano de chamadas domésticas (120 min – plano de chamadas)</li><li>**MCOPSTN6** -plano de chamadas domésticas (240 min – plano de chamadas)</li><li>**MCOMEETADD** -audioconferência</li><li>**MCOMEETACPEA** -conferência de áudio de pagamento por minuto</li></ul></li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **Filtrar** para filtrar o relatório por nome de usuário ou tipo de chamada |
|**7**   |Selecione **tela inteira** para exibir o relatório em modo de tela inteira. |
|**8**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.|

### <a name="direct-routing"></a>Roteamento Direto

![Captura de tela do relatório de uso de uso de PSTN de roteamento direto no centro de administração](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Captura de tela do relatório de uso de PSTN Routing Direct no centro de administração do Microsoft Teams com textos explicativos numerados")

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório pode ser exibido para obter tendências nos últimos sete dias ou 28 dias. |
|**2**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O eixo X é o intervalo de datas selecionado para o relatório específico. O eixo Y é o número total de chamadas durante o período de tempo selecionado.<br>Passe o mouse sobre o ponto em uma determinada data para ver o total de chamadas nessa data.  |
|**4**   |A tabela oferece uma divisão do uso de PSTN por chamada. <ul><li>**Carimbo de data/hora (UTC)** é a hora de início da chamada.</li><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams.</li><li>**Endereço SIP** é o endereço SIP do usuário que recebeu ou fez a chamada.</li><li>**Número de telefone** é o número do usuário que fez a chamada. </li><li>**Tipo de chamada** é se a chamada foi uma chamada PSTN de saída ou de entrada e o tipo de chamada, como uma chamada feita por um usuário ou uma conferência de áudio. Os tipos de chamadas que podem ser exibidas incluem:<br><br>**Tipos de chamada de usuário do teams**<ul><li>**dr_in** -o usuário recebeu uma chamada PSTN de entrada</li><li>**dr_out** -o usuário fez uma chamada PSTN de saída</li><li>**dr_out_user_conf** -o usuário adicionou um participante PSTN à chamada</li><li>**user_out_transfer** -o usuário transferiu a chamada para um número PSTN</li><li>**dr_out_user_forwarding** -o usuário encaminhou a chamada para um número PSTN</li><li>**dr_out_user_transfer** -o usuário transferiu a chamada para um número PSTN</li><li>**dr_emergency_out** -o usuário faz uma chamada de emergência</li></ul><br>**Tipos de chamada de bots do teams**<ul><li>**dr_in_ucap** -uma chamada PSTN de entrada para um bot de equipe, como atendedor automático ou fila de chamadas</li><li>**dr_out_ucap** -uma chamada PSTN de saída de um bot de equipe, como atendedor automático ou fila de chamadas</li></ul><br><li>**Chamado para** é o número do usuário que recebeu a chamada.</li><li>**Hora de início (UTC)** é a hora em que a chamada está conectada.</li><li>O **tempo de convite (UTC)** é a hora em que a chamada foi iniciada.</li><li>**Tempo de falha (UTC)** é a hora de falha na chamada. (Somente para chamadas com falha.)</li><li>**Hora de término (UTC)** é a hora em que a chamada foi encerrada. (Somente para chamadas bem-sucedidas.)</li><li>**Duração** é o tempo em que a chamada esteve conectada.</li><li>**Tipo de número** é o tipo de número de telefone do usuário, como um serviço de número de chamada gratuita. </li><li>**Bypass de mídia** indica se o tronco foi habilitado para bypass de mídia </li> <li>O o **FQDN do SBC** é o nome de domínio totalmente qualificado (FQDN) do controlador de borda de sessão (SBC). </li><li>A **região do Azure** é o datacenter usado para a sinalização.</li><li>**Tipo de evento** é o tipo de evento para a chamada. Você verá o êxito para fazer chamadas bem-sucedidas e tentar fazer chamadas com falha. </li><li>**Código SIP final** é o código com o qual a chamada foi encerrada.</li><li>**O subcódigo final da Microsoft** é um código que indica ações específicas ocorridas.</li><li>**Frase SIP final** é a descrição do código SIP e do subcódigo da Microsoft.</li><li>**COORELATION ID** é um identificador exclusivo para a chamada que você pode usar ao chamar o suporte da Microsoft.</li></ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Selecione **tela inteira** para exibir o relatório em modo de tela inteira. |

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)