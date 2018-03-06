---
title: "Ativar os recursos do Microsoft Teams na sua organização do Office 365"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Conheça todos os recursos do Microsoft Teams que você pode ativar ou desativar na sua organização do Office 365, incluindo configurações de todo o locatário, integração de email, aplicativos, armazenamento em nuvem e muito mais."
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad7af6222430f3cd3109ca76ce919a3342b959c8
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a>Ativar os recursos do Microsoft Teams na sua organização do Office 365
======================================================

O Microsoft Teams tem várias configurações que podem ser ativadas ou desativadas no nível do locatário do Office 365. Com o Microsoft Teams ativado para um locatário, qualquer usuário que também esteja habilitado para o Microsoft Teams herdará as configurações do nível do locatário.

Veja a seguir a lista de recursos que o administrador do Office 365 pode ativar ou desativar no Teams. 

A menos que esteja especificado, o valor padrão das opções é Ativado.

> [!NOTE] 
> Para gerenciar as configurações de administração no Teams, vá para o Centro de administração do Office 365 e abra **Configurações** > **Serviços e suplementos** e escolha **Microsoft Teams**. Se você tiver entrado como administrador do Office 365, este link deverá direcioná-lo corretamente: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> O administrador do Office 365 pode desativar o Microsoft Teams a qualquer momento no Centro de administração do Office 365. Esteja ciente de que os usuários com licenças ativas para o Microsoft Teams continuarão vendo o bloco do aplicativo mesmo que você o desative. Para obter detalhes sobre como remover licenças de usuários, consulte [Gerenciamento do acesso de usuários ao Microsoft Teams](user-access.md). Quando o Microsoft Teams é desabilitado, o acesso do cliente ao Microsoft Teams é bloqueado, mas os dados disponíveis por meio de outros clientes e serviços permanecem disponíveis, como arquivos via SharePoint e OneDrive. Todos os dados permanecem no lugar, a menos que as equipes sejam explicitamente excluídas.

<a name="office-365-tenant-wide-settings"></a>Configurações de todo o locatário do Office 365 
---------------------

Em **Configuração de todos os locatários**, você pode ativar e desativar opções em geral, integração de e-mails, aplicativos e armazenamento em nuvem personalizado.

Para editar as **Configurações de todo o locatário** do Microsoft Teams, acesse o Centro de administração do Office 365. Escolha **Configurações** > **Serviços e complementos** > **Microsoft Teams**.

### <a name="general"></a>Geral

A seção Geral permite que você defina as seguintes configurações para a sua organização:

> ![Captura de tela da seção Geral da Configuração de todos os locatários.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Show organizational chart in personal profile** (Mostrar organograma no perfil pessoal): quando essa configuração está ativada, é exibido o ícone do organograma no cartão de visita do usuário. Ao clicar nele, o organograma detalhado é exibido.

    ![Captura de tela do ícone do organograma no cartão de contato de um usuário.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Captura de tela de um organograma.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  **Use Skype for Business for recipients who don’t have Teams** (Usar o Skype for Business para destinatários que não têm o Teams): quando essa configuração está ativada, as conversas do Teams são exibidas automaticamente no Skype for Business para usuários que não têm o Teams.  

-   **Allow T-bot proactive help messages** (Permitir mensagens proativas de ajuda do T-Bot): quando essa configuração está ativada, o T-Bot iniciará uma sessão de chat privado com os usuários para ajudá-los a usar o Teams.

    ![Captura de tela da seção do T-Bot na interface do Microsoft Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>Integração de e-mails
-----------------

Ative esse recurso para que os usuários possam enviar emails para um canal no Microsoft Teams usando o endereço de email do canal. Os usuários podem fazer isso para qualquer canal pertencente a uma equipe que possuem. Os usuários também podem enviar e-mails para qualquer canal de uma equipe que tenha conectores adicionais habilitados para os membros da equipe. E, mesmo que um usuário não tenha permissão para criar um endereço de email de canal, se alguém que tem permissão criar esse endereço, o usuário poderá acessá-lo no menu **Mais opções** desse canal.

Defina as seguintes configurações de **integração de email** para sua organização: 

   ![Captura de tela da seção de Integração de e-mails da Configuração de todos os locatários.](media/QS-edu-email-integration.png)

-   **Allow users to send emails to channels** (Permitir que os usuários enviem emails aos canais): quando ativado, os ganchos de correio estão habilitados e os usuários podem postar mensagens em um canal enviando um email para o endereço de email do canal do Teams. 

 
-   **Allow users to send emails to channels** (Permitir que os usuários enviem emails aos canais): quando ativado, os ganchos de correio estão habilitados e os usuários podem postar mensagens em um canal enviando um email para o endereço de email do canal do Teams. 

    Para descobrir o endereço de email do canal, clique no menu **Mais opções** do canal e selecione **Obter endereço de email**. 

-   **Lista de remetentes restritos:** os domínios dos remetentes podem ser ainda mais limitados para garantir que somente os domínios SMTP permitidos possam enviar emails para os canais do Microsoft Teams.

<a name="apps"></a>Aplicativos
----

Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros. Existem políticas de administração do Teams que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos. Essas políticas permitem especificar quais aplicativos são permitidos ou não, o comportamento do novo aplicativo externo e se o sideload de aplicativos é permitido. 

Em **Aplicativos**, você pode definir estas configurações para a sua organização: 

![Captura de tela da seção de aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Allow external apps in Microsoft Teams** (Permitir aplicativos externos no Microsoft Teams): quando essa opção está ativada, os usuários podem adicionar guias e bots disponíveis para o locatário do Office 365. 
 
    ![Captura de tela do controle de permissão de aplicativos externos na seção Aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Enable new external apps by default** (Habilitar novos aplicativos externos por padrão): quando essa opção está ativada, os usuários podem ativar novos aplicativos assim que eles são adicionados ao catálogo de aplicativos do Teams. Desative essa opção para poder controlar os novos aplicativos. Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas. 

- **Allow sideloading of external apps** (Permitir o sideload de aplicativos externos): quando essa opção está ativada, os usuários podem instalar e habilitar bots e guias personalizados. 

Para saber mais, leia [Configurações de administração para aplicativos no Teams](admin-settings.md). 



<a name="custom-cloud-storage"></a>Armazenamento em nuvem personalizado
--------------------

No momento, as opções de armazenamento em nuvem do Microsoft Teams incluem Box, Dropbox, Google Drive e ShareFile. Os usuários podem carregar e compartilhar arquivos de serviços de armazenamento em nuvem nos canais e chats do Microsoft Teams. Ative a opção para os provedores de armazenamento em nuvem que sua organização deseja usar. 

![Captura de tela da seção de armazenamento em nuvem personalizado.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Configuração de usuários por licença
------------------------

Em **Configuração de usuários por licença**, você pode ativar e desativar opções de equipes e canais, chamadas e reuniões, e mensagens.

<a name="teams-and-channels"></a>Equipes e canais
------------------

Uma equipe foi designada a reunir um grupo de pessoas que trabalham em proximidade para realizar suas tarefas. As equipes podem ser dinâmicas para trabalhos baseado em projetos (por exemplo, lançamento de um produto ou criação d e uma sala de comando). Ou as equipes podem ser permanentes para refletir a estrutura interna da sua organização.

O número máximo de equipes que um locatário do Office 365 pode ter atualmente é 500.000. Um administrador global pode criar um número ilimitado de equipes. Um usuário pode criar 250 equipes. Um proprietário de equipe pode incluir 2500 membros em uma equipe.

Como administrador, você pode gerenciar proprietários e membros da equipe usando o painel de Grupos no Centro de administração do Office 365. Para saber mais, clique em **Use the Groups dashboard in the Office 365 admin center to manage teams** (Usar o painel Grupos no Centro de administração do Office 365 para gerenciar equipes) em **Equipes e canais**.

Você pode controlar quais usuários da organização podem criar equipes no Microsoft Teams. As configurações de criação definidas pelos grupos do Office 365 se aplicam ao Microsoft Teams. Para obter mais informações sobre o gerenciamento de grupos do Office 365, veja [Criar grupos no Office 365](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) e [Controlar quem pode criar Grupos no Office 365](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

> [!NOTE]
> Não é possível criar equipes a partir do painel de Grupos. As equipes devem ser criadas usando o cliente de desktop ou o aplicativo Web do Microsoft Teams.

Por padrão, qualquer usuário pode criar uma equipe ou um grupo. Escolha **Equipes** à esquerda do cliente do Microsoft Teams (cliente de desktop ou aplicativo Web) e escolha **Criar e ingressar na equipe** na parte inferior do cliente, abaixo da lista de equipes.

![Captura de tela da seção de configuração de usuários por licença.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Canais são subcategorias de equipes. Qualquer pessoa da equipe pode adicionar um canal e participar de conversas em um canal. Você pode criar um canal para uma atividade ou para um departamento. Conversas, arquivos e wikis são específicos para cada canal, mas todos os membros da equipe podem visualizá-los.

## <a name="calls-and-meetings"></a>Chamadas e reuniões

Defina as seguintes configurações de **Chamadas e reuniões** para sua organização:

![Captura de tela da seção de Chamadas e reuniões.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

O número máximo de pessoas em uma reunião é 80. Pode haver 20 membros em um bate-papo privado, incluindo o usuário que o criou.

-   **Allow scheduling for private meetings** (Permitir agendamento de reuniões privadas): quando ativado, os usuários podem agendar reuniões privadas que não estão listadas em nenhum canal.

-   **Allow ad-hoc channel meetup** (Permitir meetup de canais ad-hoc)

-   **Allow scheduling for channel meetings** (Permitir agendamento de reuniões de canais): quando ativado, os usuários podem agendar uma reunião para o canal em que todos os membros do canal podem ingressar sem dificuldades com um só clique.

-   **Allow videos in meetings** (Permitir vídeos em reuniões): especifica se é permitido usar vídeo nas reuniões.

-   **Allow screen sharing in meetings** (Permitir compartilhamento de tela em reuniões): especifica se é permitido compartilhar a tela nas reuniões.

-   **Allow private calling** (Permitir chamadas privadas): quando ativado, os usuários podem fazer chamadas privadas.

## <a name="messaging"></a>Mensagens 

A seção Mensagens permite que você defina as seguintes configurações para a sua organização:

![Captura de tela da seção de Mensagens.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Enable Giphy so users can add gifs to conversations** (Habilitar Giphy para que os usuários possam adicionas gifs às conversas): quando ativado, os usuários podem usar imagens animadas nas conversas.

-   **Classificação de conteúdo:** quando as imagens animadas estão ativadas, a classificação de conteúdo pode ser aplicada para restringir o tipo de imagens animadas que podem ser exibidas em conversas. As opções de classificação de conteúdo disponíveis são:

    -   Sem restrições
    -   Moderado (o valor padrão)
    -   Estrito

-   **Enable memes that users can edit and add to conversations** (Permitir memes que os usuários podem editar e adicionar às conversas): quando ativado, os usuários podem usar memes da Internet para fazer postagens divertidas.

-   **Enable stickers that users can edit and add to conversations** (Permitir figurinhas que os usuários podem editar e adicionar às conversas): quando ativado, os usuários podem postar imagens com texto editável para chamar a atenção dos membros do canal.

-   **Allow owners to delete all messages** (Permitir que os proprietários excluam todas as mensagens): quando ativado, os proprietários do canal podem remover todas as mensagens do canal.

-   **Allow users to edit their own messages** (Permitir que os usuários editem suas próprias mensagens): quando ativado, os usuários podem editar suas próprias mensagens.

-   **Allow users to delete their own messages** (Permitir que os usuários excluam suas próprias mensagens): quando ativado, os usuários podem excluir suas próprias mensagens.

-   **Allow users to chat privately** (Permitir que os usuários conversem de forma privada): quando ativado, os usuários podem participar de chats privados que ficam visíveis apenas para os participantes e não para todas as pessoas da equipe.


| |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Ponto de decisão         |Que configurações do Microsoft Teams a sua organização habilitará?         |
|![Ícone de próximos passos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Próximos passos        |Documente essas decisões na tabela [Atribuir funções e permissões no Microsoft Teams](assign-roles-permissions.md).         |

