---
title: Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização particular)
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
description: Use o aplicativo Microsoft Teams Learning para criar um hub central para aprender onde os funcionários podem compartilhar, atribuir e aprender nas bibliotecas de conteúdo em toda a organização.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703395"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização particular)

*Este artigo contém conteúdo preliminar para o aplicativo Teams Learning, que está em visualização particular.*

O aplicativo Microsoft Teams Learning (visualização privada) permite que equipes e indivíduos em sua organização aprendam uma parte natural do dia. O aplicativo cria um hub central no Teams em que os funcionários podem compartilhar, atribuir e aprender nas bibliotecas de conteúdo em toda a sua organização. Administradores definem permissões e permitem que as fontes de conteúdo de aprendizagem do aplicativo sejam aprendidas. O conteúdo de aprendizagem pode incluir o LinkedIn Learning, o Microsoft learn, o treinamento do Microsoft 365, o conteúdo próprio da sua organização armazenado no SharePoint Online e provedores de terceiros que são compatíveis com o aplicativo.

Para configurar o aplicativo Teams Learning (visualização particular), você precisará envolver:

-   Administrador do centro de administração do teams
-   Administrador do centro de administração do Microsoft 365 (ou seja, um administrador global)
-   Administrador de conhecimento (uma nova função no centro de administração do Microsoft 365 que um administrador global (também conhecido como administrador de ti ou administrador do Microsoft 365) pode atribuir a qualquer pessoa na organização. Esta função gerencia as fontes de conteúdo de aprendizagem da organização por meio do centro de administração do Microsoft 365.) 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Gerenciar o aplicativo Teams Learning (visualização particular) no centro de administração do teams

O administrador do teams instala o aplicativo Teams Learning (visualização particular) na App Store e aplica a configuração do aplicativo, gerenciar e políticas de permissões por meio do centro de administração do teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Gerenciar o aplicativo Teams Learning (visualização particular)

Para gerenciar as configurações do aplicativo, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.

   ![Navegação à esquerda no centro de administração do teams mostrando a seção aplicativos Teams e gerenciar aplicativos](media/learning-app-teams-manage-apps-nav.png)

2. Na página **gerenciar aplicativos** , na caixa de pesquisa, digite *Learning* para pesquisar o aplicativo Teams Learning (visualização particular).

   ![Página Gerenciar aplicativos no centro de administração do teams mostrando a caixa de pesquisa](media/learning-app-teams-manage-apps-page.png)

3. Na página de **aprendizagem** :
   1. Em **status**, selecione **permitido** para ativar o aplicativo.
   2. Na guia **configurações** , na seção **configurações do aplicativo** , vá para o centro de administração do Microsoft 365 para configurar as fontes de conteúdo de aprendizagem.

   ![Página de aprendizagem no centro de administração do teams mostrando a seção de configurações de status e de aplicativo](media/learning-app-teams-learning-page.png)

4. Após **gerenciar** as configurações do aplicativo, vá para **permissões e políticas de configuração** para conceder permissão a funcionários que devem ter acesso ao aplicativo como parte da participação da sua organização na visualização particular.

> [!NOTE]
>  Se a sua organização estiver em anel 4,0 como parte do programa Teams TAP100, talvez seja necessário fazer o seguinte para habilitar os usuários aprovados no Ring 3,0 para acessar o aplicativo Teams Learning (visualização particular).

Como parte da visualização particular, o aplicativo Teams Learning (visualização privada) é lançado em Ring 3,0. Se sua organização estiver em anel 4,0, você não verá o aplicativo na App Store. Para testar o aplicativo, você precisa criar uma política de permissão de aplicativos personalizados, defini-la para **permitir todos os aplicativos** e atribuí-la a usuários aprovados do Ring 3,0.

   ![TOQUE em-AppsPermission-Plcy página mostrar permitir todos os aplicativos selecionados](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurar fontes de conteúdo de aprendizagem no centro de administração do Microsoft 365

Os administradores do centro de administração do Microsoft 365, por si só, ou atribuindo a função de administrador de conhecimento às pessoas selecionadas em sua organização, podem gerenciar as configurações relacionadas ao aplicativo Teams Learning (visualização particular) e pode configurar as fontes de conteúdo de aprendizagem.

> [!TIP]
> O administrador de conhecimento deve ser moderado de forma moderada e ter credenciais de administrador existentes do SharePoint, de preferência a alguém que tenha uma boa conversa na educação, aprendizagem, treinamento ou experiência do funcionário da organização.
 
O administrador seleciona quais fontes de conteúdo de aprendizagem (como o LinkedIn Learning ou o SharePoint) estará disponível no aplicativo. Em seguida, o administrador configura essas fontes para garantir que o conteúdo esteja disponível para pesquisa e descoberta e possa ser acessado pelos funcionários que usam o aplicativo.

### <a name="assign-the-knowledge-admin-role-optional"></a>Atribuir a função de administrador de conhecimento [opcional]

Essas etapas devem ser executadas pelo administrador do centro de administração do Microsoft 365.

1.  Na navegação à esquerda do centro de administração do Microsoft 365, vá para **funções**.

2.  Na página **funções** , na guia **Azure ad** , selecione administrador de **conhecimento**.
 
3.  Na página **administrador de conhecimento** , na seção **Administradores atribuídos** , selecione **Adicionar** e adicione a pessoa que você escolher para a função.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Definir configurações para as fontes de conteúdo de aprendizagem do aplicativo

Essas etapas devem ser realizadas pelo administrador do Microsoft 365 ou pelo administrador de conhecimento.

1.  Na navegação à esquerda do centro de administração do Microsoft 365, vá para **configurações**  >  **organização** de configurações.

2.  Na página **configurações** , na guia **Serviços & suplementos** , selecione **aplicativo de aprendizagem**.

   ![Página configurações no centro de administração do Microsoft 365 mostrando o aplicativo de aprendizagem listado](media/learning-app-365-settings-page.png)

3.  No painel do **aplicativo de aprendizagem** , selecione as fontes de conteúdo de aprendizagem que você deseja configurar para a organização e, em seguida, selecione **salvar**.

   ![Painel do aplicativo de aprendizagem no centro de administração do Microsoft 365 mostrando opções de fontes de conteúdo](media/learning-app-365-settings-learning-app-panel.png)

Entre todas as fontes de aprendizagem existentes, algumas serão habilitadas por padrão. Elas incluem:

- LinkedIn Learning (conteúdo gratuito)
- Microsoft Learn
- Treinamento do Microsoft 365

> [!NOTE]
> Se a sua organização tiver uma assinatura do LinkedIn Learning Standard ou pro, o repositório de conteúdo será desbloqueado para os funcionários da sua organização. Somente os funcionários que têm permissão poderão usar todo o repositório de conteúdo.

Outras fontes podem precisar ser habilitadas ou configuradas manualmente. As fontes de aprendizagem que não são da Microsoft são licenciadas separadamente entre a sua organização e a outra. Você precisará verificar se inscreveu-se para seu aprendizado e seus usuários.

Para habilitar ou desabilitar uma fonte de conteúdo de aprendizagem, marque a caixa de seleção ao lado da fonte. Se uma fonte estiver habilitada, uma marca de seleção estará visível.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Configurar o SharePoint como uma fonte de conteúdo de aprendizagem

Você configura o SharePoint como uma fonte de conteúdo de aprendizagem para o aplicativo Teams Learning (visualização particular) no centro de administração do Microsoft 365.

### <a name="overview"></a>Visão geral

O administrador de conhecimento fornece uma URL de site onde o serviço de aprendizagem pode criar um repositório de conteúdo de aprendizagem centralizado vazio na forma de uma lista estruturada do SharePoint. Esta lista pode ser usada pela organização para armazenar links para pastas interempresariais do SharePoint que contenham conteúdo de aprendizagem. Os administradores são responsáveis por coletar e selecionar uma lista de URLs para pastas. Essas pastas só devem incluir conteúdo que possa ser disponibilizado no aplicativo Teams Learning (visualização particular).

### <a name="permissions"></a>Permissões

As URLs de pastas podem ser coletadas de qualquer site do SharePoint na organização. Qualquer conteúdo dentro dessas pastas será pesquisável, mas somente conteúdo para o qual o funcionário individual tem permissões pode ser usado.
 
### <a name="learning-service"></a>Serviço de aprendizagem

O serviço de aprendizagem usa as URLs de pastas fornecidas para obter metadados de todo o conteúdo armazenado nessas pastas. Dentro de 24 horas de fornecimento da URL da pasta no repositório centralizado, os funcionários podem pesquisar e usar o conteúdo da empresa dentro do aplicativo. Não há suporte para a exclusão de conteúdo do repositório neste ponto. O conteúdo na superfície não intencional pode ser removido apenas fornecendo uma nova URL de site do SharePoint no centro de administração do Microsoft 365.

### <a name="configure-sharepoint-as-a-source"></a>Configurar o SharePoint como uma origem

Essas etapas devem ser realizadas pelo administrador do Microsoft 365 ou pelo administrador de conhecimento.

1.  Na navegação à esquerda do centro de administração do Microsoft 365, vá para **configurações**.
 
2.  Na página **configurações** , na guia **Serviços & suplementos** , selecione **aplicativo de aprendizagem**.

   ![Página configurações no centro de administração do Microsoft 365 mostrando o aplicativo de aprendizagem listado](media/learning-app-365-settings-page.png)

3.  No painel do **aplicativo de aprendizagem** , forneça a URL do site para o site do SharePoint onde você deseja que o aplicativo crie um repositório centralizado.

   ![Painel do aplicativo de aprendizagem no centro de administração do Microsoft 365 mostrando o SharePoint selecionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  Uma lista do SharePoint é criada automaticamente dentro do site do SharePoint da organização fornecida. Na navegação à esquerda do site do SharePoint, selecione o **repositório de conteúdo do aplicativo de aprendizagem**. 

   ![Navegação à esquerda no SharePoint mostrando a seção repositório de conteúdo do aplicativo de aprendizagem](media/learning-app-content-repository-nav.png)

 
5. Na página **repositório de conteúdo do aplicativo de aprendizagem** , preencha a lista do SharePoint com URLs para as pastas de conteúdo de aprendizagem.

   1.   Selecione **novo** para exibir o **novo** painel de itens. 

   ![Página de repositório de conteúdo do aplicativo de aprendizagem no SharePoint mostrando a nova opção](media/learning-app-content-repository-new.png)
 
   2.   No painel **novo item** , no campo **título** , adicione o nome de um diretório de sua preferência. No campo **URL da pasta** , adicione a URL à pasta de conteúdo de aprendizagem. Selecione **Salvar**.

   ![Painel novo item no SharePoint mostrando os campos de URL título e pasta](media/learning-app-new-item-panel.png)

   3. A página do repositório de conteúdo do aplicativo de aprendizagem é atualizada com o novo conteúdo de aprendizagem.

   ![Página de repositório de conteúdo do aplicativo de aprendizagem no SharePoint mostrando as informações atualizadas](media/learning-app-content-repository-populated.png)


 


