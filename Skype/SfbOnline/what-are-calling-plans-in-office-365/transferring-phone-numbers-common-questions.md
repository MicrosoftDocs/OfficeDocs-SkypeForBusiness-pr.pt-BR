---
title: Transferindo perguntas comuns de números de telefone
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28cbf7d7-97f3-4a99-aa76-897022c14a24
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: A seguir é perguntas frequentes sobre como transferir números de telefone para Skype para negócios. Após revisar as respostas, você deve estar pronto para criar uma ordem de porta e transferir seus números de telefone. Consulte números de telefone de transferência para o Office 365 para obter instruções.
ms.openlocfilehash: ce62365c337d94c05c7ca1b3ff1703cb39086f97
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="transferring-phone-numbers-common-questions"></a>Transferindo perguntas comuns de números de telefone

A seguir é perguntas frequentes sobre como transferir números de telefone para Skype para negócios. Após revisar as respostas, você deve estar pronto para criar uma ordem de porta e transferir seus números de telefone. Para obter instruções, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md) .
  
## <a name="what-countriesregions-support-number-porting"></a>Quais países/região têm suporte para portabilidade numérica?

Você pode fazer a portabilidade ou transferir números de telefone em todos os países ou regiões compatíveis, mas como você envia uma solicitação de pedido de portabilidade depende do país ou região de onde vêm os números de telefone. Você pode ver uma lista de países/regiões que são suportados pelo [países e a disponibilidade da região para conferência de áudio e planos de chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). 

Quando estiver realizando tarefas de gerenciamento números do telefone como transferir números (portabilidade) ou introdução números de telefone que são não estão disponíveis no Skype para centro de administração de negócios, consulte [gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quais números podem ser transferidos?

 **VOCÊ PODE TRANSFERIR:**
  
Em geral, você pode transferir qualquer número de telefone que seja de um provedor compatível, incluindo:
  
- Números de telefone fixo.
    
- Números de telefone de dispositivos móveis, como aqueles usados para telefones celulares, tablets, etc.
    
    > [!NOTE]
    > [!CUIDADO] A transferência de números de celular só está disponível nos EUA e em Porto Rico. 
  
- Números de telefone de chamada tarifada.
    
- Números de telefone para chamada gratuita
    
    > [!NOTE]
    > Número de telefônico gratuito do Universal internacional (UIFN) não podem ser transferidos para nós. 
  
- Telefones de serviço como aqueles usados para pontes de conferência, atendedores automáticos, etc.
    
- Números de telefone de fax, mas que não podem ser usados para envio de fax. Eles deverão ser atribuídos a um usuário.
    
- VoIP e números de telefone de um provedor de telefonia como Vonage ou RingCentral.
    
- Skype para números de telefone comercial híbrida. Se você deseja transferir esses números, você precisa enviar email para nós em <ptn@microsoft.com>.
    
 **VOCÊ NÃO PODE TRANSFERIR:**
  
> [!NOTE]
> [!IMPORTANTE] Neste momento, não é possível transferir nenhum número de telefone que não seja de um país/região aceito, inclusive números de telefone de um provedor de telefone VoIP. Para ver uma lista de países/regiões com suporte, consulte [disponibilidade país e região para conferência de áudio e planos de chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de telefone usados para conexões de dados, como linhas DSL ou conexões com a Internet de banda larga.
    
- Números de telefone dedicados a envio e recebimento de fax.
    
    Se tem números de telefone exclusivos que estão sendo usados para fax, você  *pode*  transferi-los para o Skype for Business, mas o serviços de fax deixarão de funcionar conforme o esperado. Serviços de fax não estão disponíveis para Skype para clientes corporativos, mesmo se você tiver licenças para o **Sistema telefônico**, **Chamar domésticas planejar** ou **Internacional chamar planejar**.
    
    Se portar o número de telefone para o Skype for Business, você poderá atribuir esse número de telefone a um usuário em sua organização, em vez de usá-lo para fax.
    
> [!NOTE]
> [!CUIDADO] No momento, no Reino Unido, não damos suporte à transferência de números não geográficos do Reino Unido, incluindo números com custo compartilhado com os códigos de área 0843, 0844, 0845, 0870, 0871, 0872. 
  
## <a name="what-information-will-i-need-to-provide"></a>Que informações precisarei fornecer?

Você precisará de todas as informações da conta da operadora atual. As informações que você precisará incluir no pedido de portabilidade estão principalmente na última conta ou fatura da operadora atual. Você também precisará saber o nome que está na conta e, claro, o os números que deseja portar.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>O que são transferências de portabilidade completa e parcial?

Ao portar números de telefone para o Office 365, você tem a opção de transferir todos os seus números ou alguns deles.
  
- **Portabilidade completa** É quando você transfere todos os seus números do provedor de serviços atual para o Skype for Business Online. Quando você deve fornecer os números de telefone que deseja transferir, você *deve incluir* o número de telefone de faturamento, juntamente com todos os outros números de telefone em sua conta.
    
    Por exemplo, digamos que seu número de telefone de faturamento for *+1 425-555-1234* e você deseja porta todos os seus números de 25 telefone (*+1 425-555-1235 por meio de 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+14255551234 - +14255551259**.
    
- **Portabilidade parcial** É quando você transfere apenas alguns dos números de telefone do provedor de serviços atual para o Skype for Business Online. Se quer portar alguns dos números de telefone vinculados ao mesmo número de telefone de cobrança, você ** *não deve incluir* ** o número de telefone de cobrança com todos os outros números de telefone de sua conta.
    
    Por exemplo, digamos que seu número de telefone de faturamento (BTN) é *+1 425-555-1234* e deseja porta apenas 5 dos seus números de 25 telefone (*+1 425-555-1235 por meio de 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso enviar uma única solicitação de portabilidade para todos os meus números de uma vez?
<a name="bkmk_type_1"> </a>

É necessária uma solicitação exclusiva para cada operadora e cada tipo de número portado.
  
Por exemplo, você precisa enviar uma solicitação exclusiva de portabilidade de um número para cada um dos seguintes tipos de número:
  
- Números locais de chamada tarifada, também chamados de números de assinante ou números geográficos
    
- Números de chamada gratuita com códigos de área, como: 800, 844, 855, 866, 877 e 888
    
- Números de celular
    
- Números de serviço que podem ser usados para conferência de áudio no Office 365.
    
Veja aqui mais informações sobre como enviar solicitações de portabilidade numérica para cada um dos tipos de número:
  
- **Números de telefone** fornecidos por operadoras diferentes exigem uma solicitação de portabilidade exclusiva para os números de cada operadora.
    
- **Números de chamada gratuita** com códigos de área, como: 800, 844, 855, 866, 877 e 888, não podem ser incluídos em uma solicitação de portabilidade numérica com outros tipos de número. Para esses números de ligação gratuita de porta, você deve [manualmente enviar uma solicitação de serviço personalizado](manually-submit-a-custom-service-request.md); eles não podem ser enviados no Skype para centro de administração de negócios. Consulte [gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).
    
    É importante usar a LOA correta para o país e o tipo de números de telefone que deseja fazer a portabilidade. Você pode baixar o LOA que você precisa [Baixar a carta de autorização (LOA) que você precisa aqui](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).
    
- **Números de celular** exigem um código PIN para autorizar a transferência. Portanto, é necessária uma solicitação de portabilidade numérica separada.
    
- As solicitações de portabilidade de **números de serviço** precisam ser enviadas individualmente. Não é possível enviá-las com outros tipos de número.
    
## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo leva para portar os números?
<a name="bkmk_type_1"> </a>

Depois que você concluir o pedido de portabilidade, ele levará 7-14 dias para ser processado. No entanto, dependendo do provedor de serviços, pode levar até 30 dias. Depois que os números de telefone forem portados, você receberá um email nosso para avisar que tudo está pronto.
  
Para verificar o status do pedido de portabilidade, vá para Skype for Business centro de administração > **> Voz** > **Pedidos de portabilidade**. O status será listado na janela na coluna **Status**.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Os números de telefone do usuário (assinante) podem ser convertidos em números de serviço?
<a name="bkmk_type_1"> </a>

Sim, podem. Basta enviar uma solicitação de serviço que inclua a GUI de locatário de sua organização e os números de telefone que você deseja converter. Para fazer isso vá ver [gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
  
## <a name="common-mistakes-to-watch-out-for"></a>Erros mais comuns a serem evitados
<a name="bkmk_type_1"> </a>

A portabilidade numérica é fácil. No entanto, seu pedido pode não funcionar corretamente quando há um problema com o provedor de serviço de telefonia, o pedido está incompleto e há informações ausentes ou erros de digitação.
  
Aqui estão os erros mais comuns que os clientes cometem ao portar números. Evite uma chamada ao suporte ao cliente e verifique se esses erros ocorreram.
  
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. Informações não correspondentes são a causa mais comum de erros e atrasam o pedido de portabilidade. Verifique se o seguinte é verdadeiro:
    
  - O nome autorizado está correto.
    
  - O endereço está correto.
    
  - O número da conta está correto.
    
  - O BTN (Número de Telefone de Cobrança ) está correto.
    
- Verifique se não há recursos avançados de controle de chamadas, como Rastreamento de Chamadas ou Toque Distinto, habilitados nesses números de telefone.
    
- Verifique se você não solicitou novos serviços ou cancelamentos ao provedor de serviços atual.
    
- Verifique se todos os números são da mesma operadora e da mesma conta.
    
- Verifique se o serviço está ativo. O congelamento da conta impede a alteração de operadoras nela. O usuário autorizado precisará enviar uma solicitação à operadora atual para cancelar o congelamento. Esse processo pode levar 1-3 semanas, dependendo da operadora.
    
## <a name="can-you-transfer-or-port-out-numbers"></a>Você pode transferir ou números de porta?
<a name="bkmk_type_1"> </a>

A *porta check-out* ou transferência de números de telefone do Skype para Business Online para outro provedor de serviços telefônicos ou operadora, você precisará definir um PIN. Depois de definir o PIN, você precisará incluí-lo quando você solicitar o check-out de um número de telefone da porta. Para saber como configurar seu PIN, consulte [definir seu PIN para transferir números para um novo provedor de serviço](set-your-pin-for-transferring-numbers-to-a-new-service-provider.md).

> [!NOTE]
> Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Tópicos relacionados
[Diferentes tipos de números de telefone usados para Planos de Chamadas](../what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Termos e condições das Chamadas de Emergência](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://go.microsoft.com/fwlink/?LinkID=692099)
  
  
 
