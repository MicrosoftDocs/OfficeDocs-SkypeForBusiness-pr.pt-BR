---
title: Instalar Moodle integração com o Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 05/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Saiba como instalar e configurar o aplicativo de integração Moodle for Microsoft Teams.
keywords: As equipes Moodle plug-in de integração do aplicativo
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto: Microsoft Teams
ms.openlocfilehash: 92259a9ef01232aaeca67089b5d654fe302f1224
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2019
ms.locfileid: "34055357"
---
# <a name="install-moodle-integration-with-microsoft-teams"></a>Instalar Moodle integração com o Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), a fonte mais popular e abrir sistema de gerenciamento de aprendizado (LMS) no mundo, agora é integrado ao Microsoft Teams! Essa integração ajuda professores e professores colaboram em torno cursos Moodle, fazem perguntas sobre suas atribuições e notas e mantenha-se atualizado com as notificações – tudo dentro equipes!

Para ajudar administradores de TI a configurar facilmente dessa integração, atualizamos nosso plug-in do Office 365 Moodle de código aberto com os seguintes recursos:

- Registro automático do seu servidor Moodle com o Azure AD.
- Implantação de um clique do seu bot Moodle assistente no Azure
- O provisionamento automático de equipes e a sincronização automática de inscrições de equipe para todos ou selecione Moodle cursos
- Instalação automática da guia Moodle e o bot Moodle assistente em cada equipe sincronizado (em breve)
- Publicação de um clique do aplicativo Moodle em suas equipes App Store privada (em breve)

## <a name="prerequisites"></a>Pré-requisitos

Instalar e configurar esse aplicativo, que você precisará:

- Credenciais de administrador Moodle
- Credenciais de administrador do Azure AD
- Uma assinatura do Windows Azure que você pode criar novos recursos no

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Etapa 1: Instalar o plug-in do Office 365 Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

A integração de Moodle no Microsoft Teams é possibilitada pelo [plug-in do Office 365 Moodle](https://github.com/Microsoft/o365-moodle)de código aberto. Para instalar o plug-in no seu servidor Moodle:

1. Baixe o [plug-in Office 365 para definir](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salvá-lo no computador local. Você precisará usar a versão 3.5 ou mais recente.
2. Entrar no seu servidor Moodle como administrador e selecione **Administração do Site** no painel de navegação à esquerda.
3. Selecione a guia **Plug-ins** e clique em **Instalar plug-ins**.
4. Sob a seção de **instalar o plug-in do arquivo ZIP** , clique no botão **Escolher um arquivo** .
5. Selecione as opções de **carregar um arquivo** no painel de navegação esquerdo, navegue até o arquivo que você baixou acima e clique em **carregar este arquivo**.
6. Selecione a opção de **Administração do Site** no painel de navegação esquerdo novamente para retornar ao painel admin. Role para baixo até o **Local plug-ins** e clique no link de **Integração do Microsoft Office 365** . Mantenha esta página de configuração aberto em uma guia separada do navegador: você vai usá-lo em todo o restante desse processo.

Você pode encontrar mais informações sobre como instalar o plug-ins do Moodle na [documentação de Moodle](https://docs.moodle.org/34/en/Installing_plugins).

> [!IMPORTANT]
> Mantenha sua página de configuração de plug-in do Office 365 Moodle aberto em uma guia separada do navegador: você vai ser retornando a esse conjunto das páginas em toda esse processo.

Você não tem um site Moodle já? Talvez você queira Confira nosso Moodle no Azure [repo](https://github.com/azure/moodle) onde você pode implantar uma instância de Moodle no Azure e personalizá-lo às suas necessidades rapidamente.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Etapa 2: Configurar a conexão entre o plug-in do Office 365 e o Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Em seguida, você precisará registrar Moodle como um aplicativo em seu Windows Azure Active Directory (AD Azure). Fornecemos um script do PowerShell para ajudá-lo a concluir este processo. O script do PowerShell provisiona Azure um novo aplicativo do AD para seu locatário do Office 365, que será usado pelo Office 365 Moodle plugin. O script irá provisionar o aplicativo para seu locatário do O365, configurar todos os URLs de resposta e permissões para o aplicativo provisionado necessários e retornar a AppID e a chave. Você pode usar a AppID gerado e a chave em sua página de instalação do plug-in para O365 Moodle configurar seu servidor Moodle com o Azure AD. Se você quiser ver as etapas detalhadas manuais que o script do PowerShell é automatizando, você pode encontrá-los na [documentação do plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)completo.

1. Na página de plug-in de integração do Microsoft Office 365, selecione a guia de **instalação** .
2. Clique no botão de **Script do PowerShell de Download** e salve o script no computador local.
3. Você precisará preparar o script do PowerShell do arquivo ZIP. Para fazer isso:
    1. Baixe e extraia o arquivo Moodle-AzureAD-Powershell.zip.
    2. Abra a pasta extraída.
    3. O arquivo Moodle-AzureAD-Script.ps1 do mouse em e selecione **Propriedades**.
    4. Na guia **Geral** da caixa de diálogo Propriedades, marque a caixa de **Desbloquear** ao lado do atributo de **segurança** na parte inferior.
    5. Clique em **OK**.
    6. Copie o caminho do diretório da pasta extraído.
4. Em seguida, você executará PowerShell como um administrador:
    1. Clique em Iniciar.
    2. Tipo **PowerShell**.
    3. Clique com botão direito **do Windows PowerShell**.
    4. Clique em **Executar como administrador**.
5. Navegue até o diretório de descompactados digitando `cd ...\...\Moodle-AzureAD-Powershell` onde `...\...` é o caminho para o diretório.
6. Execute o script do PowerShell:
    1. Insira `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    2. Insira `.\Moodle-AzureAD-Script.ps1`.
    3. Inscreva-se à sua conta de administrador do O365 na janela pop-up.
    4. Insira o nome do aplicativo (por exemplo, o **plug-in Moodle/Moodle**) Azure AD.
    5. Insira a URL do seu servidor Moodle.
    6. Copie o **ID do aplicativo** e a **Tecla Application** gerados pelo script e salvá-los.
7. Em seguida, você precisará adicionar a ID e a chave para o plug-in do Office 365 Moodle. Retornar à página de administração do plug-in (**Administração do Site** > **Plug-ins** > **Integração do Microsoft Office 365**).
8. Na guia de **instalação** , adicione o **ID do aplicativo** e a **Tecla de aplicativo** você copiou anteriormente e, em seguida, clique em **Salvar alterações**.
9. Uma vez as atualizações de página, você deverá ver uma nova seção chamada o **método de conexão de escolha**. Clique a caixa de seleção **padrão**e clique em **Salvar alterações**.
10. Uma vez as atualizações de página, você verá uma nova seção denominada **& obter informações adicionais de consentimento do administrador**.
    1. Clique no link **Forneça consentimento de Admin** , insira suas credenciais de Administrador Global do 365 e escritório em casa3 e, em seguida, clique em **Aceitar** para conceder as permissões.
    2. Ao lado do campo de **Locatário do Windows Azure AD** , clique no botão **detectar** .
    3. Ao lado de **OneDrive for Business URL**, clique no botão **detectar** .
    4. Depois que os campos popular, clique no botão **Salvar as alterações** .
11. Clique no botão **Update** para verificar a instalação e, em seguida, clique em **Salvar alterações**.
12. Em seguida, você precisará sincronizar usuários entre o servidor de Moodle e o Azure AD. Dependendo do seu ambiente, você pode selecionar diferentes opções durante esse estágio. Observe que a configuração que você definir aqui será executado com cada cron Moodle executado (normalmente, uma vez por dia) para manter tudo em sincronia. Para começar:
    1. Alternar para a **guia Configurações de sincronização**.
    2. Na seção **sincronizar usuários com o Azure AD** , marque as caixas de seleção que se aplicam ao seu ambiente. Normalmente você deve selecionar pelo menos:
        - **Criar contas no Moodle para usuários no Azure AD.**
        - **Atualizar todas as contas no Moodle para usuários no Azure AD.**
    3. Na seção de **Restrição de criação de usuário** , você pode configurar um filtro para limitar os usuários do Windows Azure AD que serão sincronizados com Moodle.
    4. A seção de **Mapeamento de campo de usuário** permitirá que você personalize o Azure AD para mapeamento de campo de perfil de usuário Moodle.
    5. Na seção de **Sincronização de equipes** , você pode escolher para criar automaticamente grupos (ou seja, as equipes) para alguns ou todos os seus cursos de Moodle existentes.
13. Para validar as tarefas agendadas (e executá-los manualmente se você desejar para a primeira sequência), clique no link de **página de gerenciamento de tarefas agendadas** na seção **sincronizar usuários com o Azure AD** . Você será levado para a página de **Tarefas agendadas** .
    1. Role para baixo e localize o trabalho de **sincronizar usuários com o Azure AD** de trabalho e clique em **Executar agora**.
    2. Se você optar por criar grupos com base em cursos existentes, você também pode executar o trabalho de **criar grupos de usuários no Office 365** .
14. Retornar à página de administração do plug-in (**Administração do Site** > **Plug-ins** > **Integração do Microsoft Office 365**) e selecione a página de **Configurações de equipes** . Você precisará definir algumas configurações de segurança para habilitar a integração do aplicativo de equipes.
    1. Para habilitar OpenID conectar, clique no link **Gerenciar autenticação** e clique no ícone de olhos na linha **OpenId conectar** se ele estiver esmaecido.
    2. Para habilitar o quadro incorporação, clique no link de **HTTP de segurança** e, em seguida, marque a caixa de seleção ao lado de **permitir incorporação de quadro**.
    3. Habilite os serviços da web (o que habilitará os recursos de API Moodle). Clique no link de **Recursos avançados** e, em seguida, verifique se que a caixa de seleção ao lado de **habilitar os serviços da web** está selecionada.
    4. Habilite os serviços externos para o Office 365. Clique no link de **serviços externos** e, em seguida:
        1. Clique em **Editar** na linha **Moodle Office 365 Webservices** .
        2. Marque a caixa de seleção ao lado de **habilitado**e, em seguida, clique em **Salvar alterações**
    5. Finalmente, você precisa editar suas permissões de usuário autenticado para permitir que os usuários criem tokens de serviço da web. Clique no link do **usuário de autenticado de função de edição** . Role para baixo e encontre a capacidade de **criar um token de serviço da web** e marque a caixa de seleção **Permitir** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Etapa 3: Implantar o Bot Moodle assistente no Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

O Bot de Assistant gratuitos Moodle for Microsoft Teams ajuda professores e alunos responder às perguntas sobre seus cursos, atribuições, notas e outras informações em Moodle. O bot também envia notificações de Moodle para alunos e professores direita dentro de equipes. Este bot é um projeto de código aberto mantido pela Microsoft e está [disponível no GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
. Nesta seção, você implantará o recursos à sua assinatura do Windows Azure e todos os recursos serão configurados usando a camada de livre. Dependendo do uso do seu bot, você pode precisar expandir esses recursos. Se desejar usar apenas a guia Moodle sem o bot, pule para a [etapa 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Fluxo de informações de bot Moodle

Para instalar o bot, você precisará registrá-lo na [Plataforma do Microsoft Identity](https://identity.microsoft.com/Landing). Isso permite que sua bot autenticar com seus pontos de extremidade do Microsoft. Para registrar seu bot:

1. Retornar à página de administração do plug-in (**Administração do Site** > **Plug-ins** > **Integração do Microsoft Office 365**) e selecione a guia **Configurações de equipes** .
2. Clique no link do **Portal de registro de aplicativo Microsoft** e o logon com seu ID. Microsoft
3. Insira um nome para o aplicativo (por exemplo, MoodleBot) e clique no botão **criar** .
4. Copie o **ID do aplicativo** e colá-lo no campo **ID de aplicativo de Bot** na página **Configurações de equipe** .
5. Clique no botão **Gerar nova senha** . Copie a senha gerada e colá-lo no campo **Senha do aplicativo de Bot** na página **Configurações de equipe** .
6. Vá até o final do formulário e clique em **Save Changes**.

Agora que gerou o ID do aplicativo e a senha, é hora de implantar sua bot no Azure. Clique no botão **implantar no Windows Azure** e preencha o formulário com as informações necessárias (o bot ID e a senha são na página **Configurações de equipe** e as informações do Azure são na página **instalação** ). Uma vez que o formulário preenchido, clique na caixa de seleção para concordar com os termos e condições e, em seguida, clique no botão de **compra** (todos os recursos do Windows Azure são implantados à camada de livre).

Depois que os recursos estiverem terminados Implantando o Windows Azure, você precisará configurar o plug-in do Office 365 Moodle com seu ponto de extremidade de mensagens. Primeiro, você precisará fazer o ponto de extremidade a partir de seu bot no Windows Azure. Para fazer isso:

1. Se você não tiver entrado já, entre no [portal do Azure](https://portal.azure.com).
2. No painel esquerdo, selecione **grupos de recursos**.
3. Na lista, selecione o grupo de recursos, basta usado (ou criar) ao implantar sua bot.
4. Selecione o recurso de **WebApp Bot** da lista de recursos do grupo.
5. Copie o **Ponto de extremidade de mensagens** da seção **Visão geral** .
6. No Moodle, abra a página de **Configurações da equipe** do plug-in de Moodle do Office 365.
7. No campo de **Ponto de extremidade Bot** , cole a URL que você acabou de copiar e altere as *mensagens* do word para *webhook*. A URL agora deve se parecer com isso: `https://botname.azurewebsites.net/api/webhook`.
8. Clique em **Salvar alterações**.
9. Depois que as alterações são salvas, volte à guia **Configurações de equipe** , clique no botão de **arquivo de manifesto de Download** e salve o pacote de manifesto do computador (você vai usá-lo na próxima etapa).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Etapa 4: Implantar o seu aplicativo de equipes da Microsoft

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Agora que você tiver implantado sua bot no Windows Azure e configurado para se comunicar com seu servidor Moodle, é hora de implantar o seu aplicativo Teams da Microsoft. Para fazer isso, você vai carregar o arquivo de manifesto que você baixou da página de **Configurações de equipe** de plug-in do Office 365 Moodle na etapa anterior.

Antes de instalar o aplicativo, você precisará certificar-se de que os aplicativos externos e sideloading de aplicativos está habilitado. Para fazer isso, siga [estas etapas](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings). Depois de garantir que aplicativos externos estão habilitados, siga as etapas abaixo para implantar seu aplicativo.

1. Abra as equipes da Microsoft.
2. Clique no ícone de **repositório** no canto inferior esquerdo da barra de navegação.
3. Clique no link de **carregar um aplicativo personalizado** da lista de opções. 
   > [!NOTE]
   > Se você estiver conectado como um administrador global, você terá a opção de carregamento do aplicativo ao repositório de app da sua organização; Caso contrário, você só poderá carregar o aplicativo para que as equipes, vocês parte dos (*sideloading*).
4. Selecione o pacote de manifest.zip que você baixou anteriormente e clique em **Salvar**. Se você ainda não tenha baixado o pacote de manifesto, você poderá fazer isso na guia **Configurações de equipe** da página de configuração do plug-in na Moodle.

Agora que você tem o aplicativo instalado, você pode adicionar a guia qualquer canal que você tem acesso ao. Para fazer isso, navegue até o canal, clique no **+** símbolo e selecione seu aplicativo na lista. Siga os prompts para concluir a adição de seu guia de curso Moodle a um canal.

Isso é tudo! Você e sua equipe, agora pode começar a trabalhar com seus cursos Moodle diretamente do Microsoft Teams.

Para compartilhar quaisquer solicitações de recurso conosco ou fornecer comentários, acesse nossa [página de voz de usuário](https://microsoftteams.uservoice.com/forums/916759-moodle).