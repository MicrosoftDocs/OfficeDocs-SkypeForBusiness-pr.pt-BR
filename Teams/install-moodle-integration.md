---
title: Instalar a integração do Moodle com o Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Saiba como instalar e configurar o aplicativo LMS (sistema de gerenciamento de aprendizagem de Moodle aberto) do Microsoft Teams.
keywords: Plugin de integração do aplicativo Teams Moodle
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 984aecea4ca0be3e35a4c5eb6d09e6d3b3e49a4b
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904356"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Instalando a integração do Moodle com o Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), o sistema de gerenciamento de aprendizagem (LMS) mais popular e de código-fonte aberto do mundo agora está integrado ao Microsoft Teams! Essa integração ajuda educadores e professores a colaborar em cursos do Moodle, fazer perguntas sobre suas notas e notas e manter-se atualizado com as notificações--diretamente dentro do teams!

Para ajudar os administradores de ti a definir facilmente essa integração, atualizamos nosso plugin de Moodle de código-fonte aberto do Office 365 com os seguintes recursos:

* Registro automático do servidor do Moodle com o Azure AD.
* Implantação com um único clique do bot do assistente do Moodle para o Azure.
* Provisionamento automático de equipes e sincronização automática de registradores de equipe para todos ou selecione cursos do Moodle.
* Instalação automática da guia Moodle e do bot Assistant do Moodle em cada equipe sincronizada. (Disponível em breve)
* Publicação com um clique do aplicativo Moodle na sua loja de aplicativos particulares do Microsoft Teams. (Disponível em breve)

Para saber mais sobre a funcionalidade fornecida por essa integração, acesse [aqui](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle).

## <a name="prerequisites"></a>Pré-requisitos

Para instalar e configurar este aplicativo, você precisará:

1. Credenciais de administrador do Moodle
2. Credenciais de administrador do Azure AD
3. Uma assinatura do Azure, você pode criar novos recursos no

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Etapa 1: instalar o plugin do Office 365 Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

A integração do Moodle no Microsoft Teams é habilitada pelo [conjunto de plugin do Office 365 Moodle](https://github.com/Microsoft/o365-moodle)de abertura de fonte aberta. Para instalar o plug-in no servidor do Moodle:

1. Primeiro, baixe o [conjunto de plugin do Office 365](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salve-o em seu computador local. Você precisará usar a versão 3,5 ou mais recente.
    * Instalar o plugin local_o365 também instalará os plug-ins [auth_oidc](https://moodle.org/plugins/auth_oidc) e [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) .
1. Faça logon no seu servidor Moodle como administrador e selecione **Administração de site** no painel de navegação à esquerda.
1. Selecione a guia **plug-ins** e clique em **instalar plug-ins**.
1. Na seção **instalar plug-in do arquivo zip** , clique no botão **escolher um arquivo** .
1. Selecione as opções **carregar um arquivo** da navegação à esquerda, navegue até o arquivo que você baixou e clique em **carregar este arquivo**.
1. Selecione a opção de **Administração do site** no painel de navegação à esquerda novamente para retornar ao seu painel de administração. Role para baixo até os **plugins locais** e clique no link **integração do Microsoft Office 365** . Mantenha esta página de configuração aberta em uma guia separada do navegador, pois você a usará durante todo o restante deste processo.

Você pode encontrar mais informações sobre como instalar plug-ins Moodle na [documentação do Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Observação importante:** Mantenha a página de configuração do plugin do Office 365 Moodle aberta em uma guia separada do navegador, pois você irá retornar a este conjunto de páginas durante todo o processo.

*Ainda não tem um site do Moodle?* Convém conferir o nosso Moodle no [repositório](https://github.com/azure/moodle) do Azure, onde você pode implantar rapidamente uma instância do Moodle no Azure e personalizá-la de acordo com as suas necessidades.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Etapa 2: configurar a conexão entre o plug-in do Office 365 e o Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Em seguida, você precisará registrar o Moodle como um aplicativo no Azure Active Directory. Fornecemos um script do PowerShell para ajudá-lo a concluir esse processo. O script do PowerShell provisiona um novo aplicativo Azure AD para sua organização do Office 365, que será usado pelo plugin do Office 365 Moodle. O script provisionará o aplicativo para o seu locatário do O365, configurar todas as URLs e permissões de resposta necessárias para o aplicativo provisionado e retornar a AppID e a chave. Você pode usar a chave AppID e a chave geradas na página de configuração do plugin Moodle do O365 para configurar seu servidor Moodle com o Azure AD. Se você quiser ver as etapas manuais detalhadas que o script do PowerShell está automatizando, você pode encontrá-las na [documentação completa do plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Guia Moodle para o fluxo de informações do Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Ilustração da guia Moodle para o fluxo de informações do Microsoft Teams" />

1. Na página do plugin de integração do Microsoft Office 365 slect a guia **Configurar** .
1. Clique no botão **baixar script do PowerShell** e salve-o em seu computador local.
1. Você precisará preparar o script do PowerShell a partir do arquivo ZIP. Para fazer isso:
    * Baixe e extraia `Moodle-AzureAD-Powershell.zip` o arquivo.
    * Abra a pasta extraída.
    * Clique com o `Moodle-AzureAD-Script.ps1` botão direito do mouse no arquivo e selecione **Propriedades**.
    * Na guia **geral** da janela Propriedades, marque a `Unblock` caixa de seleção ao lado do atributo **segurança** na parte inferior.
    * Clique em **OK**.
    * Copie o caminho do diretório da pasta extraída.
1. Em seguida, execute o PowerShell como administrador:
    * Clique em Iniciar.
    * Digite PowerShell.
    * Clique com o botão direito do mouse em Windows PowerShell.
    * Clique em "executar como administrador".
1. Navegue até o diretório não compactado `cd ...\...\Moodle-AzureAD-Powershell` digitando `...\...` onde é o caminho para o diretório.
1. Executar o script do PowerShell por:
    * Enter `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Enter `.\Moodle-AzureAD-Script.ps1`.
    * Conecte-se à sua conta de administrador do O365 na janela pop-up.
    * Digite o nome do aplicativo Azure AD (por exemplo, Plugin Moodle/Moodle).
    * Digite a URL do seu Moodle Server.
    * Copie a **ID do aplicativo** e a **chave do aplicativo** gerada pelo script e salve-as.
1. Em seguida, você precisará adicionar a ID e a chave ao plugin do Office 365 Moodle. Retorne à página de administração do plugin (administração do site > plug-ins > integração do Microsoft Office 365).
1. Na guia **configuração** , adicione a **ID do aplicativo** e a **chave do aplicativo** que você copiou anteriormente e clique em **salvar alterações**.
1. Depois que a página for atualizada, você verá uma nova seção **escolher método de conexão**. Clique na caixa de seleção rotulada **como padrão** e clique em **salvar alterações** novamente.
1. Após a atualização da página, você verá outro consentimento de administrador de seção nova **& informações adicionais**.
    * Clique no link **fornecer consentimento do administrador** , insira suas credenciais de administrador global do Office3 365 e, em seguida, **aceite** para conceder as permissões.
    * Ao lado do campo **locatário do Azure ad** , clique no botão **detectar** .
    * Ao lado da **URL do onedrive for Business** , clique no botão **detectar** .
    * Depois que os campos forem preenchidos, clique no botão **salvar alterações** novamente.
1. Clique no botão **Atualizar** para verificar a instalação e, em seguida, **salve as alterações**.
1. Em seguida, você precisará sincronizar os usuários entre o servidor do Moodle e o Active Directory do Azure. Dependendo do seu ambiente, você pode selecionar opções diferentes durante esse estágio. Observe que a configuração definida aqui será executada com cada Moodle de cron (normalmente uma vez por dia) para manter tudo sincronizado. Para começar:
    * Alternar para a **guia Configurações de sincronização**
    * Na seção **sincronizar usuários com o Azure ad** , marque as caixas de seleção que se aplicam ao seu ambiente. Normalmente, você deve selecionar pelo menos:
        * Criar contas no Moodle para usuários no Azure AD
        * Atualizar todas as contas no Moodle para usuários no Azure AD
    * Na seção **restrição de criação de usuário** , você pode configurar um filtro para limitar os usuários do Azure AD que serão sincronizados com o Moodle.
    * A seção **mapeamento de campos de usuário** permitirá que você personalize o mapeamento de campos de perfil de usuário do Azure ad para Moodle.
    * Na seção **sincronização do Microsoft Teams** , você pode optar por criar automaticamente grupos (ou seja, Teams) para alguns ou todos os cursos existentes do Moodle.
1. Para validar os trabalhos cron (e executá-los manualmente, se você quiser para a primeira execução), clique no link da **página de gerenciamento de tarefas agendadas** na seção **sincronizar usuários com o Azure ad** . Isso o levará até a página **tarefas agendadas** .
    * Role a tela para baixo e localize os usuários de sincronização de trabalho com o trabalho **do Azure ad** e clique em **executar agora**.
    * Se você optou por criar grupos com base em cursos existentes, também pode executar o trabalho **criar grupos de usuários no Office 365** .
1. Retorne à página de administração do plugin (administração do site > plug-ins > Microsoft Office 365 Integration) e selecione a página **configurações do teams** . Você precisará definir algumas configurações de segurança para habilitar a integração do aplicativo Teams.
    * Para habilitar o OpenID Connect, clique no link **gerenciar autenticação** e, em seguida, clique no ícone de olho na linha do **OpenID Connect** se estiver acinzentado.
    * Em seguida, você precisará habilitar a inserção de quadros. Clique no link **segurança http** e, em seguida, clique na caixa de seleção ao lado de **permitir inserção de quadros**.
    * A próxima etapa é habilitar os serviços Web, que habilitarão os recursos de API Moodle. Clique no link **recursos avançados** e certifique-se de que a caixa de seleção ao lado de **habilitar serviços Web** esteja marcada.
    * Por fim, você precisará habilitar os serviços externos do Office 365. Clique no link de **serviços externos** e, em seguida:
        * Clique em **Editar** na linha **Moodle Office 365 WebServices** .
        * Marque a caixa de seleção ao lado de **ativado**e clique em **salvar alterações**
    * Em seguida, você precisará editar suas permissões de usuário autenticadas para permitir que elas criem tokens de serviço Web. Clique no link **"usuário autenticado da função de edição"** . Role a tela para baixo e localize a funcionalidade **criar um token de serviço Web** e marque a caixa de seleção **permitir** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Etapa 3: implantar o bot do assistente Moodle para o Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

O bot do assistente de Moodle grátis para o Microsoft Teams ajuda professores e alunos a responder perguntas sobre seus cursos, tarefas, notas e outras informações no Moodle. O bot também envia notificações Moodle para alunos e professores diretamente dentro do teams. Este bot é um projeto de código-fonte aberto mantido pela Microsoft e está [disponível no GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> Nesta seção, você implantará recursos para a sua assinatura do Azure, e todos os recursos serão configurados usando o nível **gratuito** . Dependendo do uso do bot, talvez seja necessário dimensionar esses recursos.
> Se você quiser apenas usar a guia Moodle sem o bot, pule para a [etapa 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Fluxo de informações do bot Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Ilustração do Moodle bot para o fluxo de informações do Microsoft Teams" />


Para instalar o bot, primeiro você precisa registrá-lo na [plataforma de identidade da Microsoft](https://identity.microsoft.com/Landing). Isso permite que seu bot seja autenticado em seus pontos de extremidade da Microsoft. Para registrar seu bot:

1. Retorne à página de administração do plugin (administração do site > plug-ins > integração do Microsoft Office 365) e selecione a guia **configurações do teams** .
1. Clique no link do **portal de registro de aplicativos Microsoft** e faça logon com sua ID da Microsoft.
1. Insira um nome para o aplicativo (por exemplo, MoodleBot) e clique no botão **criar** .
1. Copie a **ID do aplicativo** e cole-a no campo **ID do aplicativo bot** na página **configurações da equipe** .
1. Clique no botão **gerar nova senha** . Copie a senha gerada e cole-a no campo **senha do aplicativo bot** na página **configurações da equipe** .
1. Role até a parte inferior do formulário e clique em **salvar alterações**.

Agora que você gerou a ID do aplicativo e a senha, é hora de implantar seu bot para o Azure. Clique no botão **implantar no Azure** e preencha o formulário com as informações necessárias (a ID do aplicativo bot, a senha do aplicativo bot e o segredo Moodle estão na página **configurações da equipe** e as informações do Azure estão na página de **configuração** ). Depois de preencher o formulário, clique na caixa de seleção para concordar com os termos e condições e clique no botão **comprar** (todos os recursos do Azure são implantados no nível gratuito).

Depois que os recursos terminarem de implantar para o Azure, você precisará configurar o plugin do Moodle do Office 365 com o ponto de extremidade de mensagem. Primeiro, você precisará obter o ponto de extremidade do bot no Azure. Para fazer isso:

1. Se você ainda não tiver feito isso, faça logon no [portal do Azure](https://portal.azure.com).
2. No painel esquerdo, selecione **grupos de recursos**.
3. Na lista, selecione o grupo de recursos que você acabou de usar (ou criado) durante a implantação do bot.
4. Selecione o recurso **bot do webapp** na lista de recursos do grupo.
5. Copie o **ponto de extremidade da mensagem** na seção **visão geral** .
6. No Moodle, abra a página **configurações da equipe** do seu plugin do Moodle do Office 365.
7. No campo **ponto de extremidade do bot** , Cole a URL que você acabou de copiar e altere as *mensagens* do Word para o *webhook*. Agora a URL deve ser parecida com`https://botname.azurewebsites.net/api/webhook`
8. Clique em **salvar alterações**
9. Depois que as alterações tiverem sido salvas, volte para a guia **configurações da equipe** , clique no botão **baixar arquivo de manifesto** e salve o pacote de manifesto em seu computador (você o usará na próxima seção).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Etapa 4: implantar seu aplicativo Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Agora que você tem o seu bot implantado para o Azure e configurado para falar com seu servidor Moodle, é hora de implantar seu aplicativo Microsoft Teams. Para fazer isso, você carregará o arquivo de manifesto baixado da página Configurações da equipe do plugin do Office 365 Moodle na etapa anterior.

Antes de instalar o aplicativo, você precisará verificar se os aplicativos externos e o Sideload de aplicativos estão habilitados. Para fazer isso, você pode seguir [estas etapas](https://docs.microsoft.com/MicrosoftTeams/admin-settings). Depois de garantir que os aplicativos externos estejam habilitados, você pode seguir as etapas abaixo para implantar seu aplicativo.

1. Abra o Microsoft Teams.
2. Clique no ícone da **loja** no canto inferior esquerdo da barra de navegação.
3. Clique no link **carregar um aplicativo personalizado** na lista de opções. *Observação:* Se você estiver conectado como um administrador global, terá a opção de carregar o aplicativo na loja de aplicativos da sua organização, caso contrário, só poderá carregar o aplicativo para as equipes das quais você fizer parte ("Sideload").
4. Selecione o `manifest.zip` pacote que você baixou anteriormente e clique em **salvar**. Se você ainda não fez o download do pacote de manifesto, é possível fazer isso na guia **configurações da equipe** da página de configuração do plugin no Moodle.

Agora que você tem o aplicativo instalado, é possível adicionar a guia a qualquer canal ao qual você tenha acesso. Para fazer isso, navegue até o canal, clique **+** no símbolo e selecione seu aplicativo na lista. Siga as instruções para concluir a adição da guia curso Moodle a um canal.

Isso é tudo! Você e sua equipe agora podem começar a trabalhar com seus cursos do Moodle diretamente do Microsoft Teams.

Para compartilhar qualquer comentário ou solicitação de recursos conosco, acesse nossa [página de voz de usuários](https://microsoftteams.uservoice.com/forums/916759-moodle).