---
title: Publicar aplicativos no Catálogo de Aplicativos do Locatário do Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Orientação para a publicação de aplicativos no catálogo de aplicativos do Microsoft equipes inquilino.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebc26292e41328589f302127980f4a303efd46a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226682"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>Publicar aplicativos no Catálogo de Aplicativos do Locatário do Microsoft Teams
=======================================================

Você pode usar o catálogo de aplicativos do Microsoft equipes locatário para testar e distribuir aplicativos de linha de negócios para sua organização. 

O catálogo de aplicativos do inquilino de equipes permite que você distribuir seus aplicativos de linha de negócios que foram criados especificamente para sua organização e que você depende para concluem as funções essenciais aos negócios para seus usuários. 
 
Faça logon no seu cliente de equipes usando suas credenciais de administrador global e publicar aplicativos para sua organização. 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>Publicar um aplicativo para o catálogo de aplicativos do locatário do cliente equipes

Observação: Você precisa estar conectado ao cliente Microsoft Teams usando suas credenciais de administrador global para publicar aplicativos para sua organização.

### <a name="get-a-teams-app-package"></a>Obtenha um pacote de aplicativos de equipes

Um pacote de aplicativos de equipes é criado usando o [Studio de App equipes](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Depois que você tiver o pacote de aplicativos, você pode adicioná-lo ao catálogo de aplicativos do enterprise. Enquanto todos os usuários no locatário, pode exibir o catálogo de aplicativos, atualmente apenas globais administradores têm a capacidade de publicar e gerenciá-lo. (Eventualmente, equipes admins será capaz de fazer isso também.)

### <a name="go-to-the-tenant-apps-catalog"></a>Vá para o catálogo de aplicativos do locatário

Inicialize o cliente Microsoft Teams e entrar usando suas credenciais de administrador global. No Microsoft Teams Store, selecione nova seção denominada para sua organização específica (neste exemplo, Contoso). Usuários em sua organização podem exibir aplicativos no catálogo e instalá-los para equipes dos quais eles são membros. 

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Adicionar um aplicativo para o catálogo de aplicativos do locatário

Do repositório, selecione **carregar um aplicativo personalizado** > **Carregar para a Contoso**.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image02.png)

(Também é possível **Carregar para mim ou Minhas equipes**, que é chamado sideloading, que faz com que o aplicativo disponível somente para suas ou suas equipes selecionadas.) 

Navegue até o pacote de aplicativos e selecioná-la.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image03.png)

Quando você voltar ao seu catálogo de aplicativos do inquilino, o novo aplicativo de empresa estará lá. Lembre-se de que somente você e membros da sua organização têm acesso a esse catálogo de aplicativos.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Atualizar um aplicativo no catálogo de aplicativos do locatário

1. No seu catálogo de aplicativos do inquilino, selecione "**…**" na parte superior direita do aplicativo que você deseja atualizar.
2. Navegue até o pacote de aplicativos atualizados e selecioná-la.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image04.png)

O aplicativo será ser revisado para a versão 2.0. Você também pode excluir o aplicativo para toda a sua empresa com esse menu.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Use o portal de administração do Office 365 para gerenciar o catálogo de aplicativos do locatário

Se você tiver aplicativos que precisam correções de erros, você pode desabilitar aplicativos através do portal de administração do Office 365, selecione **configurações**temporariamente > **Serviços & complementos** > **Equipes da Microsoft**. Além das configurações anteriores, há agora uma seção dedicado aos aplicativos da sua empresa. Você pode escolher quais aplicativos que você deseja habilitar ou desabilitar.

![Captura de tela equipes App Store mostrando o catálogo de aplicativos.](media/private-app-store-teams-image05.png)

Isso impede que os usuários interajam com o aplicativo, sem excluir o aplicativo inteiramente. Esses controles fornecer flexibilidade adicional de administradores e controlar quando a governança de aplicativos em sua empresa. 


