---
title: Atribuir licenças do Microsoft Teams para educação
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Saiba como atribuir licenças para Microsoft Teams para Educação.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426798"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>Atribuir licenças do Microsoft Teams para educação

Este artigo destina-se a administradores de TI na educação que precisam atribuir licenças de equipe a seus docentes, funcionários e alunos.

Para preparar seus usuários para o Teams, você precisará:

1. [Habilite o Microsoft Teams para sua escola no Centro de administração do Microsoft 365](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Atribua licenças a contas de usuário para acesso aos serviços do Microsoft 365, incluindo o Teams.

## <a name="ways-to-assign-teams-licenses"></a>Maneiras de atribuir licenças do Teams

Você pode atribuir licenças a contas de usuário:

- Individualmente ou para um pequeno grupo de usuários no Centro de administração do Microsoft 365.
- Automaticamente por meio da associação de [grupo usando o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) ou o [licenciamento baseado em grupo do Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Este artigo explicará como atribuir licenças no Centro de administração do Microsoft 365.

No Centro de administração do Microsoft 365, você pode atribuir licenças aos usuários em:

- A **página Licenças** para atribuir licenças de produto a usuários específicos.
- A **página Usuários Ativos** para atribuir licenças de usuários a produtos específicos.

> [!NOTE]
> Você precisa ser um Administrador global, um Administrador de Cobrança ou um Administrador de Gerenciamento de Usuários. Saiba mais em [Sobre as funções de administrador do Office 365](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Atribuir licenças a usuários na página de Licenças

Na página **Licenças** , você verá uma lista de todos os produtos para os quais você tem assinaturas, o número total de licenças para cada produto, quantas licenças são atribuídas e quantas estão disponíveis.

1. No centro [de administração](https://go.microsoft.com/fwlink/p/?linkid=2024339), vá para a **página Licenças** > [de](https://go.microsoft.com/fwlink/p/?linkid=842264) Cobrança.

2. Selecione um produto para o qual você deseja atribuir licenças. O Microsoft Teams faz parte da SKU Microsoft 365 A1 para Alunos.

3. Selecione **Atribuir licenças**.

4. No painel **Atribuir licenças a usuários**, comece a digitar um nome, o que deve gerar uma lista de nomes.

5. Escolha o nome que está procurando nos resultados para adicioná-lo à lista. É possível selecionar até 20 usuários de cada vez.

6. Selecione **Ativar ou desativar os aplicativos e serviços** para atribuir ou remover o acesso a itens específicos, como o Microsoft Teams. Certifique-se de que o **Microsoft Teams** e o **Office para a Web (Educação)** estejam selecionados.

7. Quando tiver terminado, selecione **Atribuir**, e então selecione **Fechar**.

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>Alterar os aplicativos e serviços aos qual um usuário tem acesso

1. Selecione a linha que contém o usuário.

2. No painel direito, marque ou desmarque os aplicativos e serviços aos quais você deseja conceder acesso ou remover o acesso.

3. Quando tiver terminado, selecione **Salvar**, e então selecione **Fechar**.

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>Atribuir licenças a usuários na página Usuários ativos

1. No centro [de administração](https://go.microsoft.com/fwlink/p/?linkid=2024339), vá para a página **Usuários** > [Ativos](https://go.microsoft.com/fwlink/p/?linkid=834822) .

2. Selecione os círculos ao lado do(s) nome(s) do(s) usuário(s) aos quais você deseja atribuir a(s) licença(s).

3. Na parte superior, selecione **Gerenciar licenças de produto**.

4. No painel **Gerenciar licenças de produtos**, selecione **Adicionar a atribuições de licença de produto existentes** > **Avançar**.

5. No painel **Adicionar a produtos existentes**, alterne o botão para a posição **Ativado** nas licenças que você deseja que os usuários selecionados tenham. Certifique-se de que o **Microsoft Teams** e o **Office para a Web (Educação)** estejam selecionados.

   Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao(s) usuário(s). Você pode limitar quais serviços estão disponíveis para os usuários. Alterne o botão para a posição **Desativado** para os serviços que você não deseja que os usuários tenham.

6. Na parte inferior do painel, selecione **Adicionar** > **Fechar**.
