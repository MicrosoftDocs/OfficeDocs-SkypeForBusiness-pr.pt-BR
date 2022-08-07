---
title: Gerenciar dispositivos com unidades administrativas
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar unidades administrativas no Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ccc079617a1ae58b3881da8ae48c8a993d5863
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269466"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Gerenciar dispositivos no centro de administração do Teams com unidades administrativas

As unidades administrativas no centro de administração do Teams fornecem acesso detalhado e baseado em função para gerenciar dispositivos do Teams. As unidades administrativas concedem acesso de administrador do Teams a recursos específicos, mas limitam o acesso desse administrador a outros recursos. Isso é especialmente útil se você tiver administradores locais do Teams em diferentes países ou regiões.

Por exemplo, a Contoso tem operações em todo o mundo. Alice é uma administradora global de TI baseada em Londres, enquanto Prashant é uma administradora de TI local baseada em Bangalore, Índia. Hoje, quando o Prashant entra no centro de administração do Teams como administrador de dispositivos, ele pode ver dispositivos do Teams em todo o mundo. Alice deseja limitar o acesso do Prashant aos dispositivos do Teams somente em Bangalore. Unidades administrativas permitem que ela faça isso. Para saber mais, confira [Unidades administrativas no Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> No momento, as unidades administrativas estão disponíveis no centro de administração do Teams apenas para a função de administrador de dispositivos do Teams.

## <a name="add-administrative-units"></a>Adicionar unidades administrativas

Você precisa ser um administrador global para adicionar unidades administrativas. Para saber como, consulte [Adicionar uma unidade administrativa](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Atribuir administradores a unidades administrativas

Você também precisará ser administrador global para atribuir unidades administrativas. Você pode atribuir unidades administrativas usando portal do Azure, PowerShell ou o Microsoft API do Graph. Para saber mais, confira [Atribuir funções Azure AD com escopo de unidade administrativa](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Selecionar unidades administrativas

Se você for um administrador de dispositivos do Teams, depois que um administrador global atribuir você a uma unidade administrativa, você poderá entrar no centro de administração do Teams para gerenciar dispositivos. Se você estiver atribuído a apenas uma unidade administrativa, verá apenas os dispositivos atribuídos a essa unidade administrativa. Se você estiver atribuído a várias unidades administrativas, poderá alternar entre essas unidades administrativas sem sair do centro de administração do Teams. 

1. Entre no centro [de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Na caixa **de diálogo Suas unidades** administrativas, siga uma destas etapas:
    - Selecione a unidade administrativa que você deseja gerenciar ou 
    - Selecione **Todos os dispositivos** se você tiver permissão para gerenciar todos os dispositivos da sua organização.

3. Selecione **Salvar**.

## <a name="switch-administrative-units"></a>Alternar unidades administrativas

Se você for um administrador de dispositivos do Teams, poderá alternar entre unidades administrativas se estiver conectado ao centro de administração do Teams. Para alternar para uma unidade administrativa diferente:

1. Entre no centro [de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. No painel de navegação esquerdo, selecione **dispositivos do Teams**.

3. No painel direito, no canto superior esquerdo, selecione a unidade administrativa mostrada.

4. Na caixa **de diálogo Suas unidades** administrativas, siga uma destas etapas:
    - Selecione a unidade administrativa que você deseja gerenciar ou 
    - Selecione **Todos os dispositivos** se você tiver permissão para gerenciar todos os dispositivos da sua organização.

5. Selecione **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados

- [Adicionar usuários ou grupos a uma unidade administrativa](/azure/active-directory/roles/admin-units-members-add)
