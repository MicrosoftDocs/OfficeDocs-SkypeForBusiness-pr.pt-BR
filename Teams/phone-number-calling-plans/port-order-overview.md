---
title: O que é um pedido de portabilidade?
ms.author: v-lanac
author: lanachin
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
description: Obtenha uma visão geral de quais são os pedidos de portabilidade e como transferir números de telefone do seu provedor de serviços para o Microsoft Teams.
ms.openlocfilehash: 7d92c76c62405efbffaff378b2045195c175d867
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827939"
---
# <a name="whats-a-port-order"></a>O que é um pedido de portabilidade?

Se você tem atualmente um provedor de serviços de telefonia ou uma operadora e já tem números de telefone para seus usuários ou serviços, é preciso criar uma "*ordem de porta*" para transferir esses números de telefone para o Microsoft Teams. Quando os números são portados, você pode atribuir esses números de telefone aos seus usuários e serviços, como videoconferência (para pontes de conferência), atendedores automáticos e filas de chamadas.
  
Depois de portar seus números de telefone para o Microsoft Teams, a Microsoft se torna seu provedor de serviços e você pode desconectar seu serviço com seu antigo provedor de serviços ou operadora.

Revise as informações neste artigo para se familiarizar com a portabilidade de números. Depois disso, você deve estar pronto para criar um pedido de portabilidade e transferir seus números de telefone. Consulte [transferir números de telefone para o Teams](transfer-phone-numbers-to-teams.md) para obter instruções passo a passo.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quais países ou regiões dão suporte à portabilidade numérica?

Você pode portar ou transferir números de telefone em todos os países ou regiões aceitos, mas como enviar uma solicitação de pedido de portabilidade depende do país ou da região da qual os números de telefone vêm. Para obter uma lista de países e regiões que dão suporte à portabilidade de números, consulte [gerenciar números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quais números podem ser transferidos?

 **Você pode transferir**
  
Em geral, você pode transferir qualquer número de telefone de um provedor compatível, incluindo:
  
- Números de telefone fixo.

- Números de telefone de dispositivos móveis, como aqueles usados para telefones celulares e tablets.

    > [!NOTE]
    > A transferência de números de celular só está disponível nos Estados Unidos e Porto Rico.
  
- Números de telefone de chamada tarifada.

- Números de telefone para chamada gratuita

    > [!NOTE]
    > O número chamada gratuita internacional universal (UIFN) não pode ser transferido para nós. 
  
- Telefones de serviço como aqueles usados para pontes de conferência, atendedores automáticos, etc.

- Números de telefone de fax, mas que não podem ser usados para envio de fax. Elas precisam ser atribuídas a um usuário.

- VoIP e números de telefone de um provedor de telefonia como Vonage ou RingCentral.

- Números de telefone híbridos do Skype for Business. Se quiser transferir esses números, envie-nos um e-mail <ptn@microsoft.com>para.

  **Você não pode transferir:**
  
    > [!NOTE]
    > Neste momento, você não pode transferir nenhum número de telefone ou número que não seja de um país ou uma região com suporte, incluindo números de telefone de um provedor de telefonia VoIP. Para obter uma lista de países/regiões aceitos, consulte [disponibilidade de país e região para conferências de áudio e planos de chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de telefone usados para conexões de dados, como linhas DSL ou conexões com a Internet de banda larga.

- Números de telefone dedicados a envio e recebimento de fax.

    Se você tiver números de telefone dedicados existentes que estão sendo usados para o envio de fax, *poderá* transferir esses números para as equipes, mas os serviços de fax não continuarão funcionando como esperado. Os serviços de fax não estão disponíveis para os clientes do Teams, mesmo que você tenha licenças para o sistema telefônico, plano de chamadas domésticas ou plano de chamadas internacional.

    Se você portar o número de telefone para o Microsoft Teams, poderá atribuir esse número de telefone a um usuário em sua organização em vez de usá-lo para envio de fax.

    > [!NOTE]
    > No momento do Reino Unido, não oferecemos suporte para a transferência de números não geográficos do Reino Unido, incluindo números de custo compartilhado para códigos de área 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Que informações eu preciso fornecer?

Você precisa ter todas as informações da conta para a sua operadora atual. As informações que você insere na ordem das portas são encontradas na maioria das últimas faturas ou faturas do seu provedor de serviços atual. Você também precisa saber cujo nome está na conta e quais números deseja portar.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>O que são transferências de portabilidade completa e parcial?

Ao portar números de telefone para o Microsoft Teams, você tem a opção de transferir todos os seus números ou alguns deles.
  
- **Porta completa** Isso é quando você transfere todos os seus números de seu provedor de serviços atual para o Microsoft Teams. Quando for solicitado a receber os números de telefone que você deseja transferir, você *deve incluir* o número de telefone de cobrança (BTN) junto com todos os outros números de telefone na sua conta.

    Por exemplo, digamos que o seu BTN seja *+ 1 425-555-1234* e que você queira portar todos os seus 25 números de telefone (*+ 1 425-555-1235 a 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+14255551234 - +14255551259**.

- **Porta parcial** Isso ocorre quando você está apenas transferindo alguns números de telefone do provedor de serviços atual para o Microsoft Teams. Quando quiser portar alguns dos números de telefone vinculados ao mesmo BTN, você * * *não deve incluir* * * o BTN juntamente com todos os outros números de telefone na sua conta.

    Por exemplo, digamos que o BTN seja *+ 1 425-555-1234* e você queira portar apenas 5 dos seus 25 números de telefone (*+ 1 425-555-1235 a 1259*). Ao seguir as instruções abaixo para transferir os números, você deverá digitar: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso enviar uma única solicitação de portabilidade para todos os meus números de uma vez?
<a name="bkmk_type_1"> </a>

É necessária uma solicitação exclusiva para cada operadora e cada tipo de número portado.
  
Por exemplo, você precisa enviar uma solicitação exclusiva de portabilidade de um número para cada um dos seguintes tipos de número:
  
- Números de chamadas locais, também conhecidos como números de assinantes ou números geográficos

- Números de chamada gratuita com códigos de área, como: 800, 844, 855, 866, 877 e 888

- Números de celular

- Números de serviço que podem ser usados para conferências de áudio no Office 365.

Veja mais informações sobre como enviar solicitações de portabilidade de números para cada um desses tipos de números:
  
- Os **números de telefone** fornecidos por transportadoras diferentes exigem uma solicitação de portabilidade exclusiva para números com cada transportadora.

- **Números de chamada gratuita** com códigos de área, como: 800, 844, 855, 866, 877 e 888, não podem ser incluídos em uma solicitação de portabilidade de número com outros tipos de números. Para portar esses números de chamada gratuita, você deve [Enviar manualmente um pedido de portabilidade](manually-submit-port-order.md). Você não pode portar esses números no centro de administração do Microsoft Teams. Para obter mais informações, consulte [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    É importante usar a letra de autorização correta (LOA) para o país e o tipo de números de telefone que você deseja portar. Você pode [baixar o loa necessário aqui](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- **Números de celular** exigem um código PIN para autorizar a transferência. Portanto, é necessária uma solicitação de portabilidade numérica separada.

- As solicitações de portabilidade de **números de serviço** precisam ser enviadas individualmente. Eles não podem ser enviados com outros tipos de número.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo leva para portar os números?
<a name="bkmk_type_1"> </a>

Depois de concluir a solicitação de pedido de portabilidade, é preciso que entre 7-14 a dias a serem processados. No entanto, dependendo do provedor de serviços, pode levar até 30 dias. Depois que os números de telefone estiverem emportados, você receberá um e-mail de nós para lhe permitir que está pronto.
  
Para verificar o status do seu pedido de portabilidade, na navegação à esquerda do centro de administração do Microsoft Teams, vá para**números de telefone**de **voz** > e clique em histórico de **pedidos**. Cada status de pedido de portabilidade é listado na coluna **status** .
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Os números de telefone do usuário (assinante) podem ser convertidos em números de serviço?
<a name="bkmk_type_1"> </a>

Sim, podem. Basta enviar uma solicitação de serviço que inclua a GUI de locatário de sua organização e os números de telefone que você deseja converter. Para fazer isso, consulte [gerenciar números de telefone para sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="common-mistakes-to-watch-out-for"></a>Erros mais comuns a serem evitados
<a name="bkmk_type_1"> </a>

A portabilidade numérica é fácil. O seu pedido pode ficar inativo, no entanto, se houver um problema com o provedor de serviços de telefonia, o pedido é informações incompletas e ausentes, ou há erros de digitação.
  
Aqui estão os erros mais comuns que os clientes cometem ao portar números. Evite uma chamada ao suporte ao cliente e verifique se esses erros ocorreram.
  
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. Informações não correspondentes são a causa mais comum de erros e atrasam o pedido de portabilidade. Verifique se o seguinte é verdadeiro:

  - O nome ou pessoa autorizada a fazer alterações na conta está correta.

  - O endereço está correto.

  - O número da conta está correto.

  - BTN está correto.

- Certifique-se de que não haja recursos de controle de chamada avançados, por exemplo, chamadas de chamadas, toques distintos que estejam habilitados nesses números de telefone.

- Verifique se você não solicitou novos serviços ou cancelamentos ao provedor de serviços atual.

- Verifique se todos os números são da mesma operadora e da mesma conta.

- Verifique se o serviço está ativo. O congelamento da conta impede a alteração de operadoras nela. A pessoa autorizada a fazer alterações na conta deve enviar um pedido à transportadora atual para remover o congelamento. Esse processo pode levar de uma a três semanas, dependendo da operadora.

## <a name="related-topics"></a>Tópicos relacionados

- [Qual é o status dos seus pedidos de portabilidade?](port-order-status.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de isenção de isenção de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)