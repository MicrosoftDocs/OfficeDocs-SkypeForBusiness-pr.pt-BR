---
title: Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização privada)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Use o aplicativo Microsoft Teams Learning para criar um hub central para aprender onde os funcionários podem compartilhar, atribuir e aprender com bibliotecas de conteúdo em toda a organização.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6d4cb45334edb9307663eb1ffcab5e7c1085b149
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923833"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização privada)

*Este artigo contém conteúdo preliminar para o aplicativo Teams Learning, que está em visualização privada.*

O aplicativo Microsoft Teams Learning (visualização privada) capacita equipes e indivíduos em sua organização a tornar o aprendizado uma parte natural do seu dia. O aplicativo cria um hub central no Teams onde os funcionários podem compartilhar, atribuir e aprender com bibliotecas de conteúdo em toda a organização. Os administradores configuram permissões e permitem fontes de conteúdo de aprendizagem para o aplicativo. O conteúdo de aprendizagem pode incluir o LinkedIn Learning, o Microsoft Learn, o treinamento do Microsoft 365, o próprio conteúdo armazenado no SharePoint Online e provedores de terceiros que são suportados pelo aplicativo.

Para configurar o aplicativo Teams Learning (visualização privada), você precisará envolver:

-   Administrador do centro de administração do Teams
-   Administrador do Centro de administração do Microsoft 365 (ou seja, um administrador global)

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Gerenciar o aplicativo Teams Learning (visualização privada) no Centro de administração do Teams

O administrador do Teams instala o aplicativo Teams Learning (visualização privada) na loja de aplicativos e aplica políticas de configuração, gerenciamento e permissões de aplicativos por meio do Centro de administração do Teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Gerenciar o aplicativo Teams Learning (visualização privada)

Para gerenciar as configurações do aplicativo, siga estas etapas:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**

   ![Navegação à esquerda no Centro de administração do Teams mostrando os aplicativos do Teams e a seção Gerenciar aplicativos](media/learning-app-teams-manage-apps-nav.png)

2. Na página **Gerenciar aplicativos,** na caixa de pesquisa, digite o aprendizado *para* pesquisar o aplicativo Teams Learning (visualização privada).

   ![Página Gerenciar aplicativos no Centro de administração do Teams mostrando a caixa de pesquisa](media/learning-app-teams-manage-apps-page.png)

3. Na página **Aprendizagem:**
   1. Em **Status,** selecione **Permitido** ativar o aplicativo.
   2. Na guia **Configurações,** na **seção** configurações do aplicativo, vá para o Centro de administração do Microsoft 365 para configurar fontes de conteúdo de aprendizagem.

   ![Página de aprendizagem no Centro de administração do Teams mostrando a seção De status e configurações do aplicativo](media/learning-app-teams-learning-page.png)

4. Depois **de** gerenciar as configurações do aplicativo, vá para Permissões e Configurar políticas para conceder permissão aos **funcionários** que devem ter acesso ao aplicativo como parte da participação da sua organização na visualização privada.

> [!NOTE]
>  Se sua organização estiver no Ring 4.0 como parte do programa Teams TAP100, talvez seja necessário fazer o seguinte para habilitar os usuários aprovados no Ring 3.0 para acessar o aplicativo Teams Learning (visualização privada).

Como parte da visualização privada, o aplicativo Teams Learning (visualização privada) é lançado no Ring 3.0. Se sua organização estiver no Ring 4.0, você não verá o aplicativo na loja de aplicativos. Para testar o aplicativo, você precisa criar uma política de permissão de aplicativos personalizados, defini-la como Permitir todos os aplicativos e atribuí-la aos usuários aprovados do Ring 3.0.

   ![Página TAP-AppsPermission-Plcy mostrando Permitir todos os aplicativos selecionados](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurar fontes de conteúdo de aprendizagem no Centro de administração do Microsoft 365

Os administradores do Centro de administração do Microsoft 365 podem gerenciar as configurações relacionadas ao aplicativo Teams Learning (visualização privada) e podem configurar as fontes de conteúdo de aprendizagem.

O administrador seleciona quais fontes de conteúdo de aprendizagem (como o LinkedIn Learning ou o SharePoint) estarão disponíveis no aplicativo. Em seguida, o administrador configura essas fontes para garantir que o conteúdo está disponível para pesquisa e descoberta e pode ser navegado pelos funcionários que usam o aplicativo.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Configurar configurações para as fontes de conteúdo de aprendizagem do aplicativo

Estas etapas devem ser executadas pelo administrador do Microsoft 365.

1.  Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Configurações**  >  **da Organização.**

2.  Na página **Configurações,** na guia **Serviços & de complementos,** selecione **Aplicativo De aprendizagem.**

   ![Página configurações no Centro de administração do Microsoft 365 mostrando o aplicativo De aprendizagem listado](media/learning-app-365-settings-page.png)

3.  No painel **do aplicativo Aprendizagem,** selecione as fontes de conteúdo de aprendizagem que você deseja configurar para a organização e, em seguida, **selecione Salvar.**

   ![Painel de aplicativos de aprendizagem no Centro de administração do Microsoft 365 mostrando opções de fontes de conteúdo](media/learning-app-365-settings-learning-app-panel.png)

Entre todas as fontes de aprendizagem existentes, algumas serão habilitadas por padrão. Elas incluem:

- LinkedIn Learning (conteúdo gratuito)
- Microsoft Learn
- Treinamento do Microsoft 365

> [!NOTE]
> Se sua organização tiver uma assinatura do LinkedIn Learning Standard ou Pro, o repositório de conteúdo será desbloqueado para os funcionários em sua organização. Somente os funcionários que têm permissão poderão usar todo o repositório de conteúdo.

Outras fontes podem precisar ser habilitadas ou configuradas manualmente. As fontes de aprendizagem que não são da Microsoft são licenciadas separadamente entre sua organização e o terceiro. Você precisará verificar se se inscreveu para o aprendizado deles para você e seus usuários.

Para habilitar ou desabilitar uma fonte de conteúdo de aprendizagem, marque a caixa de seleção ao lado da fonte. Se uma fonte estiver habilitada, uma marca de seleção ficará visível.

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>Configurar o SharePoint como uma fonte de conteúdo de aprendizagem (em breve)

Configure o SharePoint como uma fonte de conteúdo de aprendizagem para o aplicativo Teams Learning (visualização privada) no Centro de administração do Microsoft 365.

### <a name="overview"></a>Visão Geral

O administrador fornece uma URL de site para o qual o Serviço de Aprendizagem pode criar um repositório de conteúdo de aprendizagem centralizado vazio na forma de uma lista estruturada do SharePoint. Essa lista pode ser usada pela organização para a casa de links para pastas do SharePoint entre empresas que contêm conteúdo de aprendizagem. Os administradores são responsáveis por coletar e criar uma lista de URLs para pastas. Essas pastas só devem incluir conteúdo que pode ser disponibilizado no aplicativo Teams Learning (visualização privada).

### <a name="permissions"></a>Permissões

As URLs de pastas podem ser coletadas de qualquer site do SharePoint na organização. Qualquer conteúdo dentro dessas pastas será pesquisável, mas somente o conteúdo ao qual o funcionário individual tem permissões pode ser usado.
 
### <a name="learning-service"></a>Serviço de Aprendizagem

O Serviço de Aprendizagem usa as URLs de pasta fornecidas para obter metadados de todo o conteúdo armazenado nessas pastas. Dentro de 24 horas após o fornecimento da URL da pasta no repositório centralizado, os funcionários podem pesquisar e usar o conteúdo da empresa no aplicativo. A exclusão de conteúdo do repositório não tem suporte neste momento. O conteúdo não intencionalmente superfície só pode ser removido fornecendo uma nova URL de site do SharePoint no Centro de administração do Microsoft 365.

### <a name="configure-sharepoint-as-a-source"></a>Configurar o SharePoint como fonte

Estas etapas devem ser executadas pelo administrador do Microsoft 365.

1.  Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Configurações.**
 
2.  Na página **Configurações,** na guia **Serviços & de complementos,** selecione **Aplicativo De aprendizagem.**

   ![Página configurações no Centro de administração do Microsoft 365 mostrando o aplicativo De aprendizagem listado](media/learning-app-365-settings-page.png)

3.  No painel **do aplicativo Aprendizagem,** forneça a URL do site para o site do SharePoint onde você deseja que o aplicativo crie um repositório centralizado.

   ![Painel de aplicativos de aprendizagem no Centro de administração do Microsoft 365 mostrando o SharePoint selecionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  Uma lista do SharePoint é criada automaticamente no site do SharePoint da organização fornecida. Na navegação à esquerda do site do SharePoint, selecione **Repositório de Conteúdo do Aplicativo de Aprendizagem.** 

   ![Navegação à esquerda no SharePoint mostrando a seção Repositório de Conteúdo do Aplicativo de Aprendizagem](media/learning-app-content-repository-nav.png)

 
5. Na página **Repositório de Conteúdo do** Aplicativo de Aprendizagem, preencha a lista do SharePoint com URLs para as pastas de conteúdo de aprendizagem.

   1.   Selecione **Novo** para exibir o **painel Novo item.** 

   ![Página Do Repositório de Conteúdo do Aplicativo de Aprendizagem no SharePoint mostrando a nova opção](media/learning-app-content-repository-new.png)
 
   2.   No painel **Novo item,** no campo **Título,** adicione um nome de diretório de sua escolha. No campo **URL da** Pasta, adicione a URL à pasta de conteúdo de aprendizagem. Selecione **Salvar**.

   ![Painel Novo item no SharePoint mostrando os campos DE URL de Título e Pasta](media/learning-app-new-item-panel.png)

   3. A página Repositório de Conteúdo do Aplicativo de Aprendizagem é atualizada com o novo conteúdo de aprendizagem.

   ![Página do Repositório de Conteúdo do Aplicativo de Aprendizagem no SharePoint mostrando as informações atualizadas](media/learning-app-content-repository-populated.png)


 


