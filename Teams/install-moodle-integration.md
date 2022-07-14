---
title: Instalar a integração do Moodle com o Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Saiba como instalar e configurar o aplicativo de código aberto do sistema de gerenciamento de aprendizagem Moodle para o Microsoft Teams.
keywords: Plug-in de integração do aplicativo Moodle para o Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7f0078be9f9077966fbba1a91fd569e1c4e11ec
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789536"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Instalando a integração do Moodle com o Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), o sistema de gerenciamento de aprendizagem de código aberto mais popular do mundo agora está integrado ao Microsoft Teams! Essa integração ajuda professores e alunos a colaborar em torno de cursos do Moodle, fazer perguntas sobre suas notas e tarefas e manter-se atualizado com notificações – diretamente no Teams!

Para ajudar os administradores de TI a configurar facilmente essa integração, atualizamos nosso plug-in Moodle de código aberto com os seguintes recursos:

* Registro automático do seu servidor Moodle com o Microsoft Azure Active Directory.
* Implantação em um único clique do seu bot do assistente do Moodle para o Azure.
* Provisionamento automático de equipes e sincronização automática de inscrições de equipe para cursos selecionados ou todos os cursos do Moodle.
* Instalação automática da guia Moodle e do bot do assistente do Moodle em cada equipe sincronizada. (Em breve)
* Publicação em um clique do aplicativo Moodle em sua Microsoft Store do Teams particular. (Em breve)

Para saber mais sobre a funcionalidade que essa integração oferece, confira [Instalar a integração do Moodle com o Microsoft Teams](/microsoftteams/platform/resources/moodleinstructions).

## <a name="prerequisites"></a>Pré-requisitos

Para instalar e configurar esse aplicativo, você precisará do seguinte:

1. Credenciais de administrador do Moodle
2. Credenciais de Administrador do Microsoft Azure AD
3. Uma assinatura do Microsoft Azure AD na qual você possa criar novos recursos

## <a name="step-1-install-the-moodle-plugin"></a>Etapa 1: Instalar o plug-in do Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

A integração Moodle no Microsoft Teams é produzida pelo [pacote do plug-in do Moodle](https://github.com/Microsoft/o365-moodle) de código aberto. Para instalar o plug-in no seu servidor do Moodle:

1. Primeiro, baixe o [pacote do plug-in do Moodle](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salve-o no seu computador local. Será necessário usar a versão 3.5 ou posterior.
    * Instalar o plug-in local_o365 também instalará os plug-ins [auth_oidc](https://moodle.org/plugins/auth_oidc) e [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams).
1. Entre no servidor Moodle como administrador e selecione Administração **de site** no painel de navegação esquerdo.
1. Selecione a guia **Plug-ins** e, em seguida, clique em **Instalar plug-ins**.
1. Na seção **Instalar plug-in do arquivo ZIP**, clique no botão **Escolha um arquivo**.
1. Selecione a **opção Carregar um** arquivo no painel de navegação esquerdo, procure o arquivo que você baixou acima e clique **em Carregar este arquivo**.
1. Selecione a opção **Administração do site** no painel de navegação à esquerda novamente, para retornar ao seu painel de administração. Role a tela para baixo até **Plug-ins locais** e clique no link **Integração do Microsoft Office 365**. Mantenha a página de configuração aberta em uma guia separada do navegador, pois ela será usada durante todo o restante deste processo.

Você pode encontrar mais informações sobre como instalar plug-ins do Moodle na [documentação do Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Observação importante:** manter a página de configuração do plug-in do Moodle no Microsoft 365 ou no Office 365 aberta em uma guia separada do navegador, porque você retornará a este conjunto de páginas durante todo o processo.

*Ainda não tem um site do Moodle?* Talvez você queira conferir o nosso [repositório](https://github.com/azure/moodle) do Moodle no Azure, onde é possível implantar rapidamente uma instância do Moodle no Azure e personalizá-la de acordo com as suas necessidades.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Etapa 2: configurar a conexão entre o plug-in do Microsoft 365 ou do Office 365 e o Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Em seguida, você precisará registrar o Moodle como um aplicativo no Azure Active Directory. Fornecemos um script do Windows PowerShell para ajudar você a concluir esse processo. O script do Windows PowerShell provisiona um novo aplicativo do Azure AD para a sua organização do Microsoft 365 ou do Office 365, que será usado pelo plug-in do Moodle. O script provisionará o aplicativo para seu locatário do Microsoft 365 ou do Office 365, configurará todas as URLs de respostas e de permissões necessárias para o aplicativo provisionado e retornará a AppID e a chave. Você pode usar a AppID e a chave geradas na página de configuração do plug-in do Moodle para configurar seu servidor Moodle com o Microsoft Azure Active Directory. Caso pretenda ver as etapas manuais detalhadas para a automação do script do Windows PowerShell, você pode encontrá-las na [documentação completa para o plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Guia Moodle para o fluxo de informações do Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Ilustração da guia Moodle para o fluxo de informações do Microsoft Teams" />

1. Na página do plug-in de integração do Microsoft 365 ou do Office 365, selecione a guia **Configuração**.
1. Clique no botão **Baixar script do Windows PowerShell** e salve-o no seu computador local.
1. Será necessário preparar o script do Windows PowerShell do arquivo ZIP. Para fazer isso:
    * Baixar e extrair o arquivo `Moodle-AzureAD-Powershell.zip`.
    * Abrir a pasta extraída.
    * Clique com o botão direito no arquivo `Moodle-AzureAD-Script.ps1` e selecione **Propriedades**.
    * Na guia **Geral** da janela Propriedades, marque a caixa `Unblock` ao lado do atributo **Segurança** na parte inferior.
    * Clique em **OK**.
    * Copie o caminho do diretório da pasta extraída.
1. Iniciar o Windows PowerShell como um administrador:
    * Clique em Iniciar.
    * Digite Windows PowerShell.
    * Clique com o botão direito em Windows PowerShell.
    * Clique em “Executar como administrador”.
1. Navegue até o diretório descompactado, digitando `cd ...\...\Moodle-AzureAD-Powershell` onde `...\...` é o caminho para o diretório.
1. Execute o script do Windows PowerShell:
    * Enter `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Enter `.\Moodle-AzureAD-Script.ps1`.
    * Entre na sua conta de administrador do Microsoft 365 ou do Office 365 na janela pop-up.
    * Insira o nome do aplicativo do Microsoft Azure Active Directory (Ex. plug-in Moodle/Moodle).
    * Insira a URL do seu servidor Moodle.
    * Copie a **ID do aplicativo** e a **Chave do aplicativo** gerados pelo script e salve-os.
1. Em seguida, você precisará adicionar a ID e a chave ao plug-in do Moodle. Retornar à página de administração do plug-in (Administração de site > Plug-ins > Integração do Microsoft 365).
1. Na guia **Configuração** adicione a **Identificação do aplicativo** e a **Chave do aplicativo** que você copiou anteriormente e, em seguida, clique em **Salvar alterações**.
1. Depois que a página for atualizada, você verá uma nova seção **Escolher método de conexão**. Clique na caixa de seleção rotulada **Padrão** e clique em **Salvar alterações** novamente.
1. Depois que a página for atualizada, você verá outra seção nova **Consentimento de administrador & informações adicionais**.
    * Clique no link **Fornecer consentimento de administrador**, digite suas credenciais de administrador global do Microsoft 365 ou do Office 365 e **Aceitar** para conceder as permissões.
    * Ao lado do campo **Locatário do Microsoft Azure Active Directory** e clique no botão **Detectar**.
    * Ao lado da **URL do OneDrive for Business**, clique no botão **Detectar**.
    * Após preencher os campos, clique no botão **Salvar alterações** novamente.
1. Clique no botão **Atualizar** para verificar a instalação e, em seguida, **Salvar alterações**.
1. Em seguida, você precisará sincronizar os usuários entre o servidor do Moodle e o Azure Active Directory. Dependendo do seu ambiente, você pode selecionar opções diferentes durante essa etapa. Observe que a configuração que você define aqui será executada com cada Moodle cron Run (normalmente, uma vez por dia) para manter tudo em sincronia. Para começar:
    * Alternar para a **guia Configurações de sincronização**
    * Na seção **Sincronizar usuários com o Microsoft Azure Active Directory**, marque as caixas de seleção que se aplicam ao seu ambiente. Geralmente, você selecionaria pelo menos:
        * Criar contas no Moodle para usuários no Microsoft Azure Active Directory
        * Atualizar todas as contas no Moodle para usuários no Microsoft Azure Active Directory
    * Na seção **Restrição de Criação de** Usuário, você pode configurar um filtro para limitar os Azure AD que serão sincronizados com o Moodle.
    * A seção **Mapeamento de campos de usuário** permitirá que você personalize o mapeamento do campo de perfil de usuário do Microsoft Azure Active Directory para o Moodle.
    * Na seção **Sincronização do Teams** você pode optar por criar Grupos (ou seja, Equipes) automaticamente para alguns ou todos os cursos existentes do Moodle.
1. Para validar os trabalhos cron (e executá-los manualmente se desejar para a primeira execução), clique no link **página de Gerenciamento de tarefas agendadas** na seção **Sincronizar usuários com o Microsoft Azure Active Directory**. Isso levará você para a página de **Tarefas agendadas**.
    * Role a tela para baixo e encontre o trabalho **Sincronizar usuários com o Microsoft Azure Active Directory** e clique em **Executar agora**.
    * Se você optar por criar Grupos com base em cursos existentes, também poderá executar o trabalho **Criar grupos de usuários no Office 365**.
1. Retorne à página de administração do plug-in (Administração de site > Plug-ins > Integração do Microsoft 365) e selecione a página **Configurações do Teams**. Será necessário definir algumas configurações de segurança para habilitar a integração de aplicativos do Teams.
    * Para habilitar o OpenID Connect, clique no link **Gerenciar a autenticação** e clique no ícone de olho na linha **OpenId Connect** se estiver acinzentado.
    * Em seguida, você precisará habilitar a incorporação de quadro. Clique no link **Segurança HTTP** e, em seguida, clique na caixa de seleção ao lado de **Permitir incorporação de quadro**.
    * A próxima etapa é habilitar os serviços da Web, que habilitarão os recursos da API do Moodle. Clique no link **Recursos avançados** e, em seguida, verifique se a caixa de seleção ao lado de **Habilitar serviços Web** está marcada.
    * Por fim, você precisará habilitar os serviços externos para o Microsoft 365 ou Office 365. Clique no link **Serviços externos** e, então:
        * Clique em **Editar** na linha **Moodle Office 365 Webservices**.
        * Marque a caixa de seleção ao lado de **Habilitada**, em seguida, clique em **Salvar alterações**
    * Em seguida, você precisará editar suas permissões de usuário autenticado para permitir que eles criem tokens de serviço Web. Clique no link **Editando a função 'Usuário autenticado'**. Role para baixo e localize a funcionalidade **Criar um token de serviço Web** e marque a caixa de seleção **Permitir**.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Etapa 3: implantar o bot assistente do Moodle para o Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

O bot gratuito assistente do Moodle para Microsoft Teams ajuda professores e alunos a responder a perguntas sobre cursos, tarefas, notas e outras informações no Moodle. O bot também envia notificações do Moodle aos alunos e professores dentro do Teams. Esse bot é um projeto de código aberto mantido pela Microsoft e [está disponível no GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> Nesta seção, você implantará os recursos da sua assinatura do Azure, e todos os recursos serão configurados usando o nível **gratuito**. Dependendo do uso de seu bot, talvez seja necessário escalar esses recursos.
> Se você quiser apenas usar a guia Moodle sem o bot, vá para [etapa 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Fluxo de informações do bot do Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Ilustração do bot do Moodle para o fluxo de informações do Microsoft Teams" />


Para instalar o bot, primeiro será necessário registrá-lo na [Plataforma de Identidade da Microsoft](https://identity.microsoft.com/Landing). Isso permite que o bot autentique seus pontos de extremidade da Microsoft. Para registrar seu bot:

1. Retorne à página de administração do plug-in (Administração do site > Plug-ins > Integração do Microsoft 365) e selecione a guia **Configurações do Teams**.
1. Clique no link **Portal de Registro de Aplicativos Microsoft** e efetue logon com sua ID da Microsoft.
1. Insira um nome para seu aplicativo (por exemplo, MoodleBot) e clique no botão **Criar**.
1. Copie a **ID do aplicativo** e cole-a no campo **Identificação do aplicativo bot** na página **Configurações da equipe**.
1. Clique no botão **Gerar nova senha**. Copie a senha gerada e cole-a no campo **Senha** do Aplicativo de Bot na página **Configurações da** Equipe.
1. Role até a parte inferior do formulário e clique em **Salvar alterações**.

Agora que você gerou a ID do aplicativo e a senha, chegou a hora de implantar o bot no Azure. Clique no botão **Implantar no Azure** e preencha o formulário com as informações necessárias (a ID do aplicativo bot, a senha do aplicativo bot e o segredo Moodle estão na página **Configurações da equipe** e as informações do Azure estão na página **Configuração**). Depois de preencher o formulário, marque a caixa de seleção para concordar com os termos e condições e, em seguida, clique no botão **Compra** (todos os recursos do Azure são implantados no nível gratuito).

Depois que os recursos terminarem de implantar no Azure, você precisará configurar o plug-in Moodle com seu ponto de extremidade de mensagens. Primeiro, você precisará obter o ponto de extremidade do seu bot no Azure. Para fazer isso:

1. Se você ainda não tiver feito isso, entre no [portal do Azure](https://portal.azure.com).
2. No painel esquerdo, selecione **Grupos de recursos**.
3. Na lista, selecione o grupo de recursos que você acabou de usar (ou criar) durante a implantação do bot.
4. Selecione o recurso **bot do WebApp** na lista de recursos do grupo.
5. Copie o **Ponto de extremidade de envio de mensagens** da seção **Visão geral**.
6. No Moodle, abra a página **Configurações da equipe** do seu plug-in do Moodle.
7. No campo **Ponto de extremidade do bot**, cole a URL que você acabou de copiar e altere a palavra *mensagens* para *webhook*. A URL agora deve ter a seguinte aparência `https://botname.azurewebsites.net/api/webhook`
8. Clique em **Salvar alterações**
9. Depois de salvar as alterações, volte para a guia **Configurações da equipe**, clique no botão **Baixar arquivo de manifesto** e salve o pacote de manifesto no computador (você o usará na próxima seção).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Etapa 4: implantar seu aplicativo Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Agora que você já instalou o seu bot no Azure e configurou para se comunicar com o servidor Moodle, chegou a hora de implantar o aplicativo Microsoft Teams. Para fazer isso, você carregará o arquivo de manifesto baixado da página Configurações da equipe do plug-in do Moodle na etapa anterior.

Antes de poder instalar o aplicativo, você precisará verificar se os aplicativos externos e o sideload de aplicativos estão habilitados. Para isso, siga [estas etapas](./admin-settings.md). Depois que você tiver certeza de que os aplicativos externos estão habilitados, siga as etapas abaixo para implantar o aplicativo.

1. Abra o Microsoft Teams.
2. Clique no **ícone** da Loja no canto inferior esquerdo da barra de navegação.
3. Clique no link **Carregar um aplicativo personalizado** na lista de opções. *Observação:* se você estiver conectado como um administrador global, terá a opção de carregar o aplicativo para a loja de aplicativos da sua organização. Caso contrário, você só poderá carregar o aplicativo para as equipes das quais você faz parte ("sideload").
4. Selecione o `manifest.zip` pacote baixado anteriormente e clique em **Salvar**. Caso ainda não tenha baixado o pacote de manifesto, você pode fazer isso na guia **Configurações da equipe** da página de configuração do plug-in do Moodle.

Agora que você instalou o aplicativo, você pode adicionar a guia a qualquer canal ao qual tenha acesso. Para fazer isso, navegue até o canal, clique no símbolo **+** e selecione seu aplicativo na lista. Siga as instruções para concluir a adição da guia do curso Moodle a um canal.

Isso é tudo! Você e sua equipe agora podem começar a trabalhar com seus cursos Moodle diretamente do Microsoft Teams.

Para compartilhar solicitações de recursos ou comentários conosco, visite nosso [portal de Comentários](https://feedbackportal.microsoft.com).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
