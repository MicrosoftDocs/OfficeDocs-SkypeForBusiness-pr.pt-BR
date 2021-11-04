---
title: O que é um pedido de portabilidade?
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Obter uma visão geral de quais são os pedidos de portabilidade e como transferir números de telefone de seu provedor de serviços para Teams.
ms.openlocfilehash: 936c915a79f7271ba85830122e374840f1a7050b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740237"
---
# <a name="whats-a-port-order"></a>O que é um pedido de portabilidade?

Se você atualmente tiver um provedor ou operadora de telefonia e já tiver números de telefone para seus usuários ou serviços, precisará criar uma *"* ordem de porta " para transferir esses números de telefone para Microsoft Teams. Quando os números são portados, você pode atribuir esses números de telefone aos seus usuários e serviços, como audioconferência (para pontes de conferência), atendimentos automáticos e filas de chamadas.
  
Depois que você porta seus números de telefone para Teams, a Microsoft se torna seu provedor de serviços e você pode desconectar seu serviço com seu antigo provedor de serviços ou operadora.

Revise as informações deste artigo para se familiarizar com a portação de número. Depois disso, você deve estar pronto para criar uma ordem de porta e transferir seus números de telefone. Consulte [Transfer phone numbers to Teams](transfer-phone-numbers-to-teams.md) for step-by-step instructions.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quais países ou regiões suportam a portação de números?

Você pode por ou transferir números de telefone em todos os países ou regiões com suporte, mas a forma como você envia uma solicitação de pedido de portabilidade depende do país ou região de onde os números de telefone vêm. Para uma lista de países e regiões que suportam a portação de números, consulte [Gerenciar números de telefone para sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

Atualmente, o [assistente de portação](transfer-phone-numbers-to-teams.md) no centro de administração Microsoft Teams oferece suporte para obter números de telefone para o Reino Unido, Estados Unidos e Canadá. Para obter números de telefone para outros países e regiões, você pode [enviar manualmente um pedido de porta](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quais números podem ser transferidos?

 **Você pode transferir**
  
Em geral, você pode transferir qualquer número de telefone que seja de um provedor com suporte, incluindo:
  
- Números de telefone fixo.

- Números de telefone de dispositivo móvel, como os usados para celulares e tablets.

    > [!NOTE]
    > A transferência de números móveis só está disponível nos Estados Unidos e em Porto Rico.
  
- Números de telefone de chamada tarifada.

- Números de telefone para chamada gratuita

    > [!NOTE]
    > O Número Universal de Telefone Livre (UIFN) não pode ser transferido para nós. 
  
- Telefones de serviço como aqueles usados para pontes de conferência, atendedores automáticos, etc.

- Números de telefone de fax, mas que não podem ser usados para envio de fax. Eles precisam ser atribuídos a um usuário.

- VoIP e números de telefone de um provedor de telefonia como Vonage ou RingCentral.

- Skype for Business números de telefone híbridos. Se você quiser transferir esses números, envie um email para <ptn@microsoft.com> .

  **Não é possível transferir:**
  
    > [!NOTE]
    > No momento, você não pode transferir nenhum número de telefone ou números que não sejam de um país ou região com suporte, incluindo números de telefone de um provedor de telefonia VoIP. Para ver uma lista de países/regiões com suporte, consulte Disponibilidade de país e [região para Planos de Audioconferência e Chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de telefone usados para conexões de dados, como linhas DSL ou conexões com a Internet de banda larga.

- Números de telefone dedicados a envio e recebimento de fax.

    Se você tiver números de telefone dedicados existentes  que estão sendo usados para fax, você pode transferir esses números para Teams, mas seus serviços de fax não continuarão a funcionar conforme esperado. Os serviços de fax não estão disponíveis para clientes Teams, mesmo que você tenha licenças para Sistema de Telefonia, Plano de Chamada Doméstica ou Plano de Chamada Internacional.

    Se você porta o número de telefone para Teams, você pode atribuir esse número de telefone a um usuário em sua organização em vez de usá-lo para fax.

    > [!NOTE]
    > Atualmente, no Reino Unido, não há suporte para a transferência de números não geográficos do Reino Unido, incluindo números de custo compartilhados para códigos de área 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quais informações preciso fornecer?

Você precisa ter todas as informações da conta para sua operadora atual. As informações que você inserir na ordem de porta são encontradas principalmente na fatura ou fatura mais recente do provedor de serviços atual. Você também precisa saber qual nome está na conta e quais números deseja portar.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>O que são transferências de portabilidade completa e parcial?

Ao portar números de telefone para Teams, você tem a opção de transferir todos os números ou alguns deles.
  
- **Porta inteira** Isso é quando você transfere todos os números do seu provedor de serviços atual para Teams. Quando for solicitado os números de telefone que  deseja transferir, inclua o número de telefone de cobrança (BTN) juntamente com todos os outros números de telefone em sua conta.

    Por exemplo, digamos que seu BTN  *seja +1 425-555-1234*  e você deseja por todos os seus 25 números de telefone (*+1 425-555-1235 a 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+14255551234 - +14255551259**.

- **Porta parcial** Isso é quando você está transferindo apenas alguns dos seus números de telefone do seu provedor de serviços atual para Teams. Quando você deseja por alguns dos números de telefone vinculados ao mesmo BTN, você **** não deve incluir ** o BTN juntamente com todos os outros números de telefone em sua conta.

    Por exemplo, digamos que seu BTN  *é +1 425-555-1234*  e você deseja por apenas 5 dos seus 25 números de telefone (*+1 425-555-1235 a 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso enviar uma única solicitação de portabilidade para todos os meus números de uma vez?
<a name="bkmk_type_1"> </a>

É necessária uma solicitação exclusiva para cada operadora e cada tipo de número portado.
  
Por exemplo, você precisa enviar uma solicitação exclusiva de portabilidade de um número para cada um dos seguintes tipos de número:
  
- Números de chamada local, também conhecidos como números de assinantes ou números geográficos

- Números de chamada gratuita com códigos de área, como: 800, 844, 855, 866, 877 e 888

- Números de celular

- Números de serviço que podem ser usados para Audioconferência em Microsoft 365 ou Office 365.

Veja mais informações sobre como enviar solicitações de portação de número para cada um desses tipos de números:
  
- **Telefone números fornecidos** por diferentes operadoras exigem uma solicitação de portação exclusiva para números com cada operadora.

- Números **gratuitos** com códigos de área, como: 800, 844, 855, 866, 877 e 888 não podem ser incluídos em uma solicitação de portação de número com outros tipos de números. Para portabilidade desses números gratuitos, você [deve enviar manualmente um pedido de portabilidade](manually-submit-port-order.md). Você não pode por esses números no centro de Microsoft Teams de administração. Para obter mais informações, consulte [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    É importante usar a LOA (Carta de Autorização) correta para o país e o tipo de números de telefone que você deseja portar. Você pode [baixar a LOA de que precisa aqui](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- **Números de celular** exigem um código PIN para autorizar a transferência. Portanto, é necessária uma solicitação de portabilidade numérica separada.

- As solicitações de portabilidade de **números de serviço** precisam ser enviadas individualmente. Eles não podem ser enviados com outros tipos de números.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo leva para portar os números?
<a name="bkmk_type_1"> </a>

Depois de concluir a solicitação de pedido de portabilidade, leva de 7 a 14 dias para ser processado. No entanto, dependendo do provedor de serviços, pode levar até 30 dias. Depois que os números de telefone são portados, você receberá um email nosso para que você saiba que você pode ir.
  
Para verificar o status da sua ordem de porta, na navegação à esquerda do centro de administração Microsoft Teams, vá para **Números** Telefone voz e clique em  >  Histórico de **pedido**. Cada status do pedido de porta está listado na **coluna Status.**
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Os números de telefone do usuário (assinante) podem ser convertidos em números de serviço?
<a name="bkmk_type_1"> </a>

Sim, podem. Basta enviar uma solicitação de serviço que inclua a GUI de locatário de sua organização e os números de telefone que você deseja converter. Para fazer isso, consulte [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Posso por meus números de Teams para um provedor ou operadora de telefonia diferente?

Para fazer a portabilidade de seus números Teams para uma operadora diferente, você deve enviar uma solicitação com a nova operadora. Você também precisará definir um PIN de portação no Microsoft Teams de administração.

Para definir seu PIN de portação, na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Números** de voz Telefone , no canto superior direito da página, selecione Gerenciar PIN de portação e insira um PIN de  >  10 dígitos. 

Quando a nova operadora entrar em contato conosco com a solicitação de portação, pediremos que forneçam o PIN definido.

## <a name="common-mistakes-to-watch-out-for"></a>Erros mais comuns a serem evitados
<a name="bkmk_type_1"> </a>

A portabilidade numérica é fácil. Seu pedido pode ficar confuso, no entanto, se houver um problema com o provedor de serviço de telefonia, o pedido está incompleto e faltando informações, ou há erros de digitação.
  
Aqui estão os erros mais comuns que os clientes cometem ao portar números. Evite uma chamada ao suporte ao cliente e verifique se esses erros ocorreram.
  
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. Informações não correspondentes são a causa mais comum de erros e atrasam o pedido de portabilidade. Verifique se o seguinte é verdadeiro:

  - O nome ou a pessoa autorizada a fazer alterações na conta está correto.

  - O endereço está correto.

  - O número da conta está correto.

  - BTN está correto.

- Certifique-se de que não há recursos avançados de controle de chamadas, por exemplo, Busca de Chamadas, Anel Distinto, que estão habilitados nesses números de telefone.

- Verifique se você não solicitou novos serviços ou cancelamentos ao provedor de serviços atual.

- Verifique se todos os números são da mesma operadora e da mesma conta.

- Verifique se o serviço está ativo. O congelamento da conta impede a alteração de operadoras nela. A pessoa autorizada a fazer alterações na conta deve enviar um pedido à operadora atual para remover o congelamento. Esse processo pode levar de uma a três semanas, dependendo da operadora.

## <a name="related-topics"></a>Tópicos relacionados

- [Qual é o status dos seus pedidos de portabilidade?](port-order-status.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
