---
title: Gerenciar dispositivos com unidades administrativas
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar unidades administrativas em Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Gerenciar dispositivos no centro de administração Teams com unidades administrativas

As unidades administrativas no Teams de administração fornecem acesso detalhado e baseado em função para gerenciar Teams dispositivos. As unidades administrativas Teams acesso de administrador a recursos específicos, mas limitam o acesso desse administrador a outros recursos. Isso é especialmente útil se você tiver administradores Teams locais em diferentes países ou regiões.

Por exemplo, a Contoso tem operações ao redor do mundo. Alice é um administrador de IT global com base em Londres, enquanto Prashant é um administrador de IT local com base em Bangalore, Índia. Hoje, quando Prashant entra no centro de administração Teams como administrador de dispositivos, ele pode ver Teams dispositivos em todo o mundo. Alice deseja limitar o acesso de Prashant a dispositivos Teams somente em Bangalore. Unidades administrativas permitem que ela faça isso. Para saber mais, confira [Unidades administrativas em Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> No momento, as unidades administrativas estão disponíveis no centro de administração Teams apenas para a função de administrador Teams dispositivos.

## <a name="add-administrative-units"></a>Adicionar unidades administrativas

Você precisa ser um administrador global para adicionar unidades administrativas. Para saber como, confira [Adicionar uma unidade administrativa](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Atribuir administradores a unidades administrativas

Você também precisará ser administrador global para atribuir unidades administrativas. Você pode atribuir unidades administrativas usando o portal do Azure, o PowerShell ou a API Graph Microsoft. Para saber mais, confira [Atribuir funções do Azure AD com escopo de unidade administrativa](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Selecionar unidades administrativas

Se você for um administrador de dispositivos Teams, depois que um administrador global atribuí-lo a uma unidade administrativa, você poderá entrar no centro de administração Teams para gerenciar dispositivos. Se você for atribuído a apenas uma unidade administrativa, verá apenas os dispositivos atribuídos a essa unidade administrativa. Se você for atribuído a várias unidades administrativas, poderá alternar entre essas unidades administrativas sem sair do Teams de administração. 

1. Entre no centro de [Teams de administração](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Na caixa **de diálogo Suas unidades administrativas** , siga uma destas etapas:
    - Selecione a unidade administrativa que você deseja gerenciar ou 
    - Selecione **Todos os** dispositivos se você tiver permissão para gerenciar todos os dispositivos da sua organização.

3. Selecione **Salvar**.

## <a name="switch-administrative-units"></a>Alternar unidades administrativas

Se você for um administrador de dispositivos Teams, poderá alternar entre unidades administrativas se estiver conectado ao centro de administração Teams local. Para alternar para uma unidade administrativa diferente:

1. Entre no centro de [Teams de administração](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Na navegação à esquerda, selecione **Teams dispositivos**.

3. No painel direito, no canto superior esquerdo, selecione a unidade administrativa mostrada.

4. Na caixa **de diálogo Suas unidades administrativas** , siga uma destas etapas:
    - Selecione a unidade administrativa que você deseja gerenciar ou 
    - Selecione **Todos os** dispositivos se você tiver permissão para gerenciar todos os dispositivos da sua organização.

5. Selecione **Salvar**.
