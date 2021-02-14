---
title: O que é um pedido de portabilidade?
ms.author: v-cichur
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Obter uma visão geral sobre o que são pedidos de portabilidade e como transferir números de telefone de seu provedor de serviços para o Teams.
ms.openlocfilehash: 4f1f8ca843db8c2b27eaa467b0014befe6f2b519
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802501"
---
# <a name="whats-a-port-order"></a>O que é um pedido de portabilidade?

Se você tem um provedor de serviços de telefonia ou operadora e já tem números de telefone para seus usuários ou serviços, precisa criar um *"* pedido de portabilidade " para transferir esses números de telefone para o Microsoft Teams. Quando os números são portados, você pode atribuir esses números de telefone aos seus usuários e serviços, como audioconferência (para pontes de conferência), atender automaticamente e filas de chamadas.
  
Depois que você porta seus números de telefone para o Teams, a Microsoft torna-se seu provedor de serviços e você pode desconectar seu serviço com seu provedor de serviços ou operadora antigo.

Revise as informações neste artigo para se familiarizar com a portação de números. Depois disso, você deverá estar pronto para criar um pedido de portabilidade e transferir seus números de telefone. Consulte [Transferir números de telefone para o Teams](transfer-phone-numbers-to-teams.md) para obter instruções passo a passo.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quais países ou regiões suportam a portagem de números?

Você pode fazer a portabilidade ou a transferência de números de telefone em todos os países ou regiões com suporte, mas a forma como você envia uma solicitação de pedido de portabilidade depende do país ou da região de origem dos números de telefone. Para ver uma lista de países e regiões que suportam portação de números, consulte Gerenciar números [de telefone para sua organização.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Atualmente, o [assistente de portação](transfer-phone-numbers-to-teams.md) no Centro de administração do Microsoft Teams dá suporte à adoção de números de telefone para o Reino Unido, Estados Unidos e Canadá. Para obter números de telefone para outros países e regiões, você pode [enviar manualmente um pedido de portabilidade.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>Quais números podem ser transferidos?

 **Você pode transferir**
  
Em geral, você pode transferir qualquer número de telefone de um provedor com suporte, incluindo:
  
- Números de telefone fixo.

- Números de telefone de dispositivo móvel, como os usados para celulares e tablets.

    > [!NOTE]
    > A transferência de números de celular só está disponível nos Estados Unidos e em Porto Rico.
  
- Números de telefone de chamada tarifada.

- Números de telefone para chamada gratuita

    > [!NOTE]
    > Não é possível transferir o Número Universal Internacional de Telefone Livre (UIFN). 
  
- Telefones de serviço como aqueles usados para pontes de conferência, atendedores automáticos, etc.

- Números de telefone de fax, mas que não podem ser usados para envio de fax. Eles devem ser atribuídos a um usuário.

- VoIP e números de telefone de um provedor de telefonia como Vonage ou RingCentral.

- Números de telefone híbridos do Skype for Business. Se você quiser transferir esses números, envie-nos um email <ptn@microsoft.com> para.

  **Não é possível transferir:**
  
    > [!NOTE]
    > No momento, não é possível transferir nenhum número de telefone ou números que não sejam de um país ou região com suporte, incluindo números de telefone de um provedor de telefonia VoIP. Para ver uma lista de países/regiões com suporte, consulte a disponibilidade de país e região para Planos [de Audioconferência e Chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de telefone usados para conexões de dados, como linhas DSL ou conexões com a Internet de banda larga.

- Números de telefone dedicados a envio e recebimento de fax.

    Se você tiver números de telefone dedicados que  estão sendo usados para enviar fax, poderá transferir esses números para o Teams, mas seus serviços de fax não continuarão a funcionar conforme o esperado. Os serviços de fax não estão disponíveis para clientes do Teams, mesmo que você tenha licenças para o Sistema de Telefonia, Plano de Chamada Doméstica ou Plano de Chamada Internacional.

    Se você portar o número de telefone para o Teams, poderá atribuir esse número de telefone a um usuário em sua organização em vez de usá-lo para enviar fax.

    > [!NOTE]
    > Atualmente, no Reino Unido, não há suporte para transferência de números não geográficos do Reino Unido, incluindo números de custo compartilhados para os códigos de área 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quais informações preciso fornecer?

Você precisa ter todas as informações da conta da operadora atual. As informações que você inserir no pedido de portabilidade são encontradas principalmente na fatura ou na fatura mais recente do provedor de serviços atual. Você também precisa saber qual nome está na conta e quais números deseja por portabilidade.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>O que são transferências de portabilidade completa e parcial?

Ao portar números de telefone para o Teams, você tem a opção de transferir todos os seus números ou alguns deles.
  
- **Portabilidade completa** É quando você transfere todos os seus números do provedor de serviços atual para o Teams. Quando você for solicitado a transferir os números  de telefone, deverá incluir o número de telefone de cobrança (BTN) juntamente com todos os outros números de telefone em sua conta.

    Por exemplo, digamos que seu BTN seja *+1 425-555-1234* e você queira portugue todos os seus 25 números de telefone *(+1 425-555-1235 a 1259).* Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+14255551234 - +14255551259**.

- **Portabilidade parcial** É quando você transfere apenas alguns de seus números de telefone do provedor de serviços atual para o Teams. Quando você quiser portugue alguns dos números de telefone vinculados ao mesmo BTN, **** não deverá incluir ** o BTN juntamente com todos os outros números de telefone em sua conta.

    Por exemplo, digamos que seu BTN seja *+1 425-555-1234* e você queira por 5 de seus 25 números de telefone *(+1 425-555-1235 a 1259).* Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso enviar uma única solicitação de portabilidade para todos os meus números de uma vez?
<a name="bkmk_type_1"> </a>

É necessária uma solicitação exclusiva para cada operadora e cada tipo de número portado.
  
Por exemplo, você precisa enviar uma solicitação exclusiva de portabilidade de um número para cada um dos seguintes tipos de número:
  
- Números de chamada tarifada local, também conhecidos como números de assinantes ou números geográficos

- Números de chamada gratuita com códigos de área, como: 800, 844, 855, 866, 877 e 888

- Números de celular

- Números de serviço que podem ser usados para Audioconferência no Microsoft 365 ou no Office 365.

Veja mais informações sobre como enviar solicitações de portação de número para cada um desses tipos de números:
  
- **Os números de** telefone fornecidos por operadoras diferentes exigem uma solicitação de portação exclusiva para números com cada operadora.

- Números **de** tarifa gratuita com códigos de área como: 800, 844, 855, 866, 877 e 888 não podem ser incluídos em uma solicitação de portação de número com outros tipos de números. Para fazer a portabilidade desses números de tarifa gratuita, você [deve enviar manualmente um pedido de portabilidade.](manually-submit-port-order.md) Não é possível fazer a portabilidade desses números no Centro de administração do Microsoft Teams. Para obter mais informações, consulte [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    É importante usar a LOA (Carta de Autorização) correta para o país e o tipo de números de telefone que você deseja fazer a portabilidade. Você pode [baixar a LOA de que precisa aqui.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **Números de celular** exigem um código PIN para autorizar a transferência. Portanto, é necessária uma solicitação de portabilidade numérica separada.

- As solicitações de portabilidade de **números de serviço** precisam ser enviadas individualmente. Eles não podem ser enviados com outros tipos de números.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo leva para portar os números?
<a name="bkmk_type_1"> </a>

Depois de concluir a solicitação de pedido de portabilidade, leva de 7 a 14 dias para ser processado. No entanto, dependendo do provedor de serviços, pode levar até 30 dias. Depois que os números de telefone são portados, você vai receber um email nosso para deixar que você esteja tudo certo.
  
Para verificar o status do seu pedido de portabilidade, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para números de Telefone De Voz e clique em  >  Histórico **de pedido.** Cada status do pedido de portabilidade é listado na **coluna Status.**
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Os números de telefone do usuário (assinante) podem ser convertidos em números de serviço?
<a name="bkmk_type_1"> </a>

Sim, podem. Basta enviar uma solicitação de serviço que inclua a GUI de locatário de sua organização e os números de telefone que você deseja converter. Para fazer isso, consulte [Gerenciar números de telefone para sua organização.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Posso fazer a portabilidade de meus números do Teams para outro provedor de serviços de telefonia ou operadora?

Para enviar seus números do Teams para outra operadora, você deve enviar uma solicitação com a nova operadora. Você também precisará definir um PIN de portação no Centro de administração do Microsoft Teams.

Para definir seu PIN de portação, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para números de Telefone De Voz, no canto superior direito da página, selecione Gerenciar PIN de portação e insira um PIN de  >  10 dígitos. 

Quando sua nova operadora entrar em contato conosco com a solicitação de portação, solicitaremos que ela forneça o PIN que você definiu.

## <a name="common-mistakes-to-watch-out-for"></a>Erros mais comuns a serem evitados
<a name="bkmk_type_1"> </a>

A portabilidade numérica é fácil. Seu pedido pode ficar confuso, no entanto, se houver um problema com o provedor de serviços de telefonia, o pedido está incompleto e faltando informações, ou há erros de digitação.
  
Aqui estão os erros mais comuns que os clientes cometem ao portar números. Evite uma chamada ao suporte ao cliente e verifique se esses erros ocorreram.
  
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. Informações não correspondentes são a causa mais comum de erros e atrasam o pedido de portabilidade. Verifique se o seguinte é verdadeiro:

  - O nome ou a pessoa autorizada a fazer alterações na conta está correta.

  - O endereço está correto.

  - O número da conta está correto.

  - BTN está correto.

- Certifique-se de que não haja recursos avançados de controle de chamada, por exemplo, a Busca de Chamadas, Toque Diferenciado, que estão habilitados nesses números de telefone.

- Verifique se você não solicitou novos serviços ou cancelamentos ao provedor de serviços atual.

- Verifique se todos os números são da mesma operadora e da mesma conta.

- Verifique se o serviço está ativo. O congelamento da conta impede a alteração de operadoras nela. A pessoa autorizada a fazer alterações na conta deve enviar um pedido à operadora atual para remover o congelamento. Esse processo pode levar de uma a três semanas, dependendo da operadora.

## <a name="related-topics"></a>Tópicos relacionados

- [Qual é o status dos seus pedidos de portabilidade?](port-order-status.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)