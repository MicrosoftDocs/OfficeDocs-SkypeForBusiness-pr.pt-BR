---
title: Gerenciar o Microsoft equipes privados App Store
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Diretrizes para o gerenciamento de aplicativos no Microsoft Teams privados app store.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a2a7e4be22878cf0625077b23fad388b38bc9e
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19576942"
---
<a name="manage-the-microsoft-teams-private-app-store"></a>Gerenciar o Microsoft equipes privados App Store
============================================

> [!IMPORTANT]
> Esta página descreve um recurso de pré-lançamento e contém conteúdo preliminar que pode ser alterado substancialmente antes do lançamento. Qualquer capturas de tela são espaços reservados e podem parecer diferentes de que você vê.

Você pode usar o Microsoft Teams Private App Store para criar e distribuir seus aplicativos de linha de negócios para sua organização. 

Microsoft Teams Private App Store permite que você distribuir seus aplicativos de linha de negócios que foram criados especificamente para sua organização e que você depende para concluem as funções essenciais aos negócios para seus usuários. 
 
Há dois métodos para gerenciar equipes privados App Store:
- Diretamente a partir do cliente de equipes 
- Cmdlets que aproveitam APIs do Microsoft Graph (esse método ainda não está disponível.)

## <a name="manage-the-teams-private-app-store-from-the-teams-client"></a>Gerenciar equipes privados App Store do cliente equipes

### <a name="get-a-teams-app-package"></a>Obtenha um pacote de aplicativos de equipes

Um pacote de aplicativos de equipes é criado usando o [Studio de App equipes](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio). Depois que você tiver o pacote de aplicativos, você pode adicioná-lo ao catálogo de aplicativos do enterprise. Enquanto todos os usuários no inquilino podem exibir o catálogo de aplicativos, apenas administradores têm a capacidade de gerenciar a ele.

### <a name="go-to-the-teams-private-app-store"></a>Vá para equipes privados App Store

No Microsoft Teams Store, selecione nova seção denominada para sua organização específica (neste exemplo, Contoso). Usuários em sua organização podem exibir aplicativos no catálogo e instalá-los para equipes dos quais eles são membros. 

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a>Adicionar um aplicativo para equipes privados App Store

Do repositório, selecione **carregar um aplicativo personalizado** > **Carregar para a Contoso**.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

(Também é possível **Carregar para mim ou Minhas equipes**, que é chamado sideloading, que faz com que o aplicativo disponível somente para suas ou suas equipes selecionadas.) 

Navegue até o pacote de aplicativos e selecioná-la.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

Quando você voltar ao seu catálogo de aplicativos, o novo aplicativo de empresa estará lá. Lembre-se de que somente você e membros da sua organização têm acesso a esse catálogo de aplicativos.

### <a name="update-an-app-in-the-teams-private-app-store"></a>Atualizar um aplicativo na App Store equipes privado

1. No seu catálogo de aplicativos, selecione "**…**" na parte superior direita do aplicativo que você deseja atualizar.
2. Navegue até o pacote de aplicativos atualizados e selecioná-la.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

O aplicativo será ser revisado para a versão 2.0. Você também pode excluir o aplicativo para toda a sua empresa com esse menu.

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a>Gerenciar equipes privados App Store usando cmdlets e APIs do Microsoft Graph

Este método ainda não está disponível para visualização.

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a>Usar o portal de administração do Office 365 para gerenciar aplicativos de privado

Se você tiver aplicativos que precisam correções de erros, você pode desabilitar temporariamente aplicativos através do portal de administração do Office 365. Além das configurações anteriores, há agora uma seção dedicado aos aplicativos da sua empresa. Você pode escolher quais aplicativos que você deseja habilitar ou desabilitar.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

Isso impede que os usuários interajam com o aplicativo, sem excluir o aplicativo inteiramente. Esses controles fornecer flexibilidade adicional de administradores e controlar quando a governança de aplicativos em sua empresa. 


