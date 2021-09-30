---
title: Obter números de telefone para seus usuários
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Saiba como obter novos, porta ou transferir números existentes para Teams e como mostrar as alterações aos seus usuários.
ms.openlocfilehash: 09b42acef400f28760c50cd8a570f5c1cb1e3392
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012105"
---
# <a name="getting-phone-numbers-for-your-users"></a>Obter números de telefone para seus usuários

Antes de configurar usuários em sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.
  
Há três maneiras de obter números de usuário:

- **Use o Microsoft Teams de administração.** Para alguns países e regiões, você pode obter números para seus usuários usando o Microsoft Teams de administração. Consulte [Obter novos números de telefone para seus usuários](#get-new-phone-numbers-for-your-users).

- **Fazer a portabilidade de seus números existentes.** Você pode por ou transferir números existentes de seu provedor de serviços ou operadora de telefonia atual. Consulte [Transferir os números dos telefones ao Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [Gerenciar números de telefone da sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações.  
  
- **Usar um formulário de solicitação para novos números.** Às vezes (dependendo do seu país ou região), você não poderá obter seus novos números de telefone usando o Centro de Administração Microsoft Teams ou precisará de números de telefone ou códigos de área específicos. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> Se você precisar de ajuda para configurar números de telefone para sua organização, entre em contato [com o Support Contact for Business Products - Ajuda do administrador.](/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)
  
## <a name="get-new-phone-numbers-for-your-users"></a>Obtenha novos números de telefone para seus usuários

![Um ícone mostrando o logotipo do Microsoft Teams.](media/teams-logo-30x30.png) **Usando centro de administração do Microsoft Teams**

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Vá para o Microsoft Teams Admin Center.

2. Na navegação à esquerda, vá para **Voz**  >  **Telefone números** e clique em **Adicionar**.

3. Insira um nome para a ordem e adicione uma descrição.

4. Na página Local e quantidade, faça o seguinte:
    1. Em **País ou região**, selecione um país ou região.
    2. Em **Tipo de número,** selecione **Usuário (assinante)**.
    3. Em **Local**, selecione um local. Se precisar criar um novo local, clique em **Adicionar um local**.
    4. Em **Código de área,** selecione um código de área.
    5. Em **Quantidade**, insira o número de números que você deseja para sua organização e clique em **Próximo** para selecionar seus números.

5. Selecione os números que você deseja. Você tem 10 minutos para selecionar seus números de telefone e fazer o pedido. Se você demorar mais de 10 minutos, os números de telefone serão retornados para o pool de números.

6. Quando estiver pronto para fazer seu pedido, clique em **Colocar ordem**.

    > [!IMPORTANT]
    > O número de números de telefone para usuários (assinantes) é igual  ao número total de licenças do Plano de Chamadas Domésticas e/ou do Plano de Chamadas Domésticas e Internacionais que você atribuiu multiplicado por 1,1, além de 10 números de telefone adicionais.  Por exemplo, se você tiver 50 usuários no total com um Plano De Chamadas Domésticas e/ou um Plano de Chamadas Domésticas e Internacionais, você pode adquirir **65** números de telefone **(50 x 1,1 + 10)**. Para obter detalhes, [consulte Quantos números de telefone você pode obter?](./how-many-phone-numbers-can-you-get.md). Se você precisar obter mais números de telefone do que isso, entre em [contato com o Support Contact for Business Products - Ajuda do administrador.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Fazer a portabilidade ou transferir os números de telefone de seu provedor de serviços ou de sua operadora de telefonia
  
- Se você precisar de 999 ou menos números de telefone para seus usuários, use o assistente de portação no Microsoft Teams Admin Center. Siga as etapas em [Transferir números de telefone para Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Se seu país ou região não estiver listado no assistente de portabilidade, [](/microsoftteams/manage-phone-numbers-for-your-organization) você poderá enviar [manualmente](phone-number-calling-plans/manually-submit-port-order.md) um pedido de porta ou ver Gerenciar números de telefone para sua organização baixar a Carta de Autorização correta (LOA).

- Se você precisar por mais de 999 números de telefone, envie [manualmente](phone-number-calling-plans/manually-submit-port-order.md) um pedido de porta ou consulte [Gerenciar](/microsoftteams/manage-phone-numbers-for-your-organization) números de telefone da sua organização para baixar a LOA (Carta de Autorização) correta e enviá-la para o service [desk PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) para obter todos os seus números transferidos.

## <a name="view-the-phone-numbers-for-your-organization"></a>Exibir os números de telefone para sua organização

![Um ícone mostrando o logotipo do Microsoft Teams.](media/teams-logo-30x30.png) **Usando centro de administração do Microsoft Teams**

Na navegação à esquerda do centro de administração, vá até **Voz** Telefone números para exibir os números da sua organização, incluindo informações de localização, tipo de  >   número e status.
  
## <a name="assign-phone-numbers-to-users"></a>Atribuir números de telefone aos usuários

Depois de obter seus números de telefone, você precisará atribuir um número a cada um dos seus usuários. Confira [Atribuir, alterar ou remover um número de telefone para um usuário](./assign-change-or-remove-a-phone-number-for-a-user.md) para obter mais informações.

> [!NOTE]
> Se você precisar obter mais números de telefone do que isso, entre em [contato com o Support Contact for Business Products - Ajuda do administrador.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)

## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)