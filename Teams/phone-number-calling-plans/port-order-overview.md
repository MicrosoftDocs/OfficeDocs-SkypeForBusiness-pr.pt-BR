---
title: O que é um pedido de portabilidade?
author: CarolynRowe
ms.author: crowe
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
description: Obtenha uma visão geral do que são pedidos de portabilidade e como transferir números de telefone de seu provedor de serviços para o Teams.
ms.collection:
- M365-voice
- m365initiative-voice
ms.openlocfilehash: e9f267bfdb56558245fecefe240f2c09c07d4783
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270866"
---
# <a name="whats-a-port-order"></a>O que é um pedido de portabilidade?

Se você tiver um provedor de serviços de telefonia ou uma operadora e já tiver números de telefone para seus usuários ou serviços, precisará criar *um "pedido* de portabilidade" para transferir esses números de telefone para o Microsoft Teams. Quando os números são transferidos, você pode atribuir esses números de telefone aos usuários e serviços, como audioconferência (para pontes de conferência), atendedores automáticos e filas de chamadas.
  
Depois de portar seus números de telefone para o Teams, a Microsoft se tornará seu provedor de serviços e você poderá desconectar seu serviço com seu antigo provedor de serviços ou operadora.

Examine as informações neste artigo para se familiarizar com a portabilidade de número. Depois disso, você deve estar pronto para criar um pedido de portabilidade e transferir seus números de telefone. Consulte [Transferir números de telefone para o Teams](transfer-phone-numbers-to-teams.md) para obter instruções passo a passo.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quais países ou regiões dão suporte à portabilidade de números?

Você pode portar ou transferir números de telefone em todos os países ou regiões com suporte, mas a maneira como você envia uma solicitação de pedido de portabilidade depende do país ou região de onde vêm os números de telefone. Para obter uma lista de países e regiões que dão suporte à portabilidade de números, consulte [Gerenciar números de telefone para sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

Atualmente, o [assistente de portabilidade](transfer-phone-numbers-to-teams.md) no Centro de administração do Microsoft Teams dá suporte à aquiação de números de telefone para o Reino Unido, Estados Unidos e Canadá. Para obter números de telefone para outros países e regiões, você pode [enviar manualmente um pedido de portabilidade](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quais números podem ser transferidos?

 **Você pode transferir**
  
Em geral, você pode transferir qualquer número de telefone de um provedor com suporte, incluindo:
  
- Números de telefone fixo.

- Números de telefone de dispositivo móvel, como aqueles usados para celulares e tablets.

    > [!NOTE]
    > A transferência de números de celular só está disponível no Estados Unidos e em Porto Rico.
  
- Números de telefone de chamada tarifada.

- Números de telefone para chamada gratuita

    > [!NOTE]
    > O UIFN (Número Universal de Telefone Livre Internacional) não pode ser transferido para nós.
    > A disponibilidade de portabilidade para números de telefone gratuitos pode variar de acordo com o país e a região. Para saber mais, consulte os documentos específicos do seu país ou região para ver o suporte disponível para portabilidade do serviço. 
  
- Telefones de serviço como aqueles usados para pontes de conferência, atendedores automáticos, etc.

- Números de telefone de fax, mas que não podem ser usados para envio de fax. Eles precisam ser atribuídos a um usuário.

- VoIP e números de telefone de um provedor de telefonia como Vonage ou RingCentral.

- Se você estiver portando números de telefone híbridos (migrando do Roteamento Direto ou da Conexão do Operador para Planos de Chamadas), entre em contato com a Equipe de Serviços de Número de [Telefone,](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) certifique-se de incluir uma nota informando que eles são números de telefone híbridos.

**Não é possível transferir:**
  
> [!NOTE]
> No momento, você não pode transferir nenhum número de telefone ou números que não sejam de um país ou região com suporte, incluindo números de telefone de um provedor de telefonia VoIP. Para obter uma lista de países/regiões com suporte, consulte Disponibilidade de país e região [para Audioconferência e Planos de Chamadas](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de telefone usados para conexões de dados, como linhas DSL ou conexões com a Internet de banda larga.

- Números de telefone dedicados a envio e recebimento de fax.

    Se você tiver números de telefone dedicados existentes que estão sendo usados para fax,  poderá transferir esses números para o Teams, mas os serviços de fax não continuarão funcionando conforme o esperado. Os serviços de fax não estão disponíveis para os clientes do Teams, mesmo que você tenha licenças para o Sistema de Telefonia, o Plano de Chamadas Domésticas ou o Plano de Chamadas Internacionais.

    Se você portar o número de telefone para o Teams, poderá atribuir esse número de telefone a um usuário em sua organização em vez de usá-lo para fax.

> [!NOTE]
> Atualmente, no Reino Unido, não há suporte para transferência de números não geográficos do Reino Unido, incluindo números de custo compartilhados para códigos de área 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quais informações preciso fornecer?

Você precisa ter todas as informações de conta para sua operadora atual. As informações inseridas no pedido de portabilidade são encontradas principalmente na fatura ou na fatura mais recente do provedor de serviços atual. Você também precisa saber qual nome está na conta e quais números você deseja portar.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>O que são transferências de portabilidade completa e parcial?

Ao portar números de telefone para o Teams, você tem a opção de transferir todos os seus números ou alguns deles.
  
- **Porta completa** Isso ocorre quando você transfere todos os seus números do seu provedor de serviços atual para o Teams. Quando você for solicitado a fornecer os números de telefone que deseja transferir, deverá  incluir o BTN (número de telefone de cobrança) junto com todos os outros números de telefone em sua conta.

    Por exemplo, digamos que o BTN seja  *+1 425-555-1234*  e você queira portar todos os seus 25 números de telefone (*+1 425-555-1235 a 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+14255551234 - +14255551259**.

- **Porta parcial** Isso ocorre quando você está transferindo apenas alguns de seus números de telefone do seu provedor de serviços atual para o Teams. Quando você deseja portar alguns dos números de telefone vinculados ao mesmo BTN, *** não* deve incluir ** o BTN junto com todos os outros números de telefone em sua conta.

    Por exemplo, digamos que o BTN é  *+1 425-555-1234*  e você deseja portar apenas 5 de seus 25 números de telefone (*+1 425-555-1235 a 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso enviar uma única solicitação de portabilidade para todos os meus números de uma vez?
<a name="bkmk_type_1"> </a>

É necessária uma solicitação exclusiva para cada operadora e cada tipo de número portado.
  
Por exemplo, você precisa enviar uma solicitação exclusiva de portabilidade de um número para cada um dos seguintes tipos de número:
  
- Números de pedágio locais, também conhecidos como números de assinante ou números geográficos

- Números de chamada gratuita com códigos de área, como: 800, 844, 855, 866, 877 e 888

- Números de celular

- Números de serviço que podem ser usados para Audioconferência no Microsoft 365 ou Office 365.

Veja mais informações sobre como enviar solicitações de portabilidade de número para cada um desses tipos de números:
  
- **Os números de** telefone fornecidos por operadoras diferentes exigem uma solicitação de portabilidade exclusiva para números com cada operadora.

- Números **de** chamada gratuita com códigos de área como: 800, 844, 855, 866, 877 e 888 não podem ser incluídos em uma solicitação de portabilidade de número com outros tipos de números. Para portar esses números de chamada gratuita, você deve [enviar manualmente um pedido de portabilidade](manually-submit-port-order.md). Não é possível portar esses números no centro de administração do Microsoft Teams. Para obter mais informações, consulte [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    É importante usar a LOA (Carta de Autorização) correta para o país e o tipo de números de telefone que você deseja portar. Você pode [baixar a LOA de que precisa aqui](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- **Números de celular** exigem um código PIN para autorizar a transferência. Portanto, é necessária uma solicitação de portabilidade numérica separada.

- As solicitações de portabilidade de **números de serviço** precisam ser enviadas individualmente. Eles não podem ser enviados com outros tipos de números.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo leva para portar os números?
<a name="bkmk_type_1"> </a>

Depois de concluir a solicitação de pedido de portabilidade, leva de 7 a 14 dias para ser processado. No entanto, dependendo do provedor de serviços, pode levar até 30 dias. Depois que os números de telefone forem transferidos, você receberá um email nosso para informar que você está pronto para começar.
  
Para verificar o status do pedido de portabilidade, no painel de navegação esquerdo do Centro de administração do Microsoft Teams,  >  vá para números de Telefone de Voz e clique em **Histórico de pedidos**. Cada status do pedido de portabilidade é listado na **coluna Status** .
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Os números de telefone do usuário (assinante) podem ser convertidos em números de serviço?
<a name="bkmk_type_1"> </a>

Sim, podem. Basta enviar uma solicitação de serviço que inclua a GUI de locatário de sua organização e os números de telefone que você deseja converter. Para fazer isso, consulte [Gerenciar números de telefone para sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Posso portar meus números do Teams para uma operadora ou provedor de serviços de telefonia diferente?

Para portar seus números do Teams para uma operadora diferente, você deve enviar uma solicitação com a nova operadora. Você também precisará definir um PIN de portabilidade no centro de administração do Microsoft Teams.

Para definir o PIN de portabilidade, no painel de navegação esquerdo do Centro de administração do Microsoft Teams,  >  vá para números de Telefone de **Voz, no** canto superior direito da página, selecione Gerenciar PIN de portabilidade e insira um **PIN** de 10 dígitos.

Quando sua nova operadora entrar em contato conosco com a solicitação de portabilidade, solicitaremos que ela forneça o PIN que você definiu.

Se você precisar de mais assitância configurando um PIN, entre em contato com a Equipe [de Serviços de Número de Telefone](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>Erros mais comuns a serem evitados
<a name="bkmk_type_1"> </a>

A portabilidade numérica é fácil. Seu pedido pode ficar confuso, no entanto, se houver um problema com o provedor de serviços de telefonia, o pedido está incompleto e as informações ausentes ou há erros de digitação.
  
Aqui estão os erros mais comuns que os clientes cometem ao portar números. Evite uma chamada ao suporte ao cliente e verifique se esses erros ocorreram.
  
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. Informações não correspondentes são a causa mais comum de erros e atrasam o pedido de portabilidade. Verifique se o seguinte é verdadeiro:

  - O nome ou a pessoa autorizada a fazer alterações na conta está correto.

  - O endereço está correto.

  - O número da conta está correto.

  - BTN está correto.

- Verifique se não há recursos avançados de controle de chamada, por exemplo, Busca de Chamadas, Anel Distinto, que estão habilitados nesses números de telefone.

- Verifique se você não solicitou novos serviços ou cancelamentos ao provedor de serviços atual.

- Verifique se todos os números são da mesma operadora e da mesma conta.

- Verifique se o serviço está ativo. O congelamento da conta impede a alteração de operadoras nela. A pessoa autorizada a fazer alterações na conta deve enviar um pedido à operadora atual para remover o congelamento. Esse processo pode levar de uma a três semanas, dependendo da operadora.

## <a name="related-topics"></a>Tópicos relacionados

- [Qual é o status dos seus pedidos de portabilidade?](port-order-status.md)
- [Diferentes tipos de números de telefone utilizados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
