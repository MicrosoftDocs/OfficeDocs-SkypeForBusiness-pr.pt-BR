---
title: "Ativar os recursos do Microsoft Teams na sua organização do Office 365"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Conheça todos os recursos do Microsoft Teams que você pode ativar na sua organização do Office 365, incluindo configurações de todo o locatário, integração de email, aplicativos, armazenamento em nuvem e muito mais."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: d6a4a8d10e20b57df16fac3c7ffeba0bacd64d2e
ms.sourcegitcommit: 19d7af5d60276c0a1ca3e01588b91c34a3fd0f92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a>Ativar os recursos do Microsoft Teams na sua organização do Office 365
======================================================

O Microsoft Teams tem várias configurações que podem ser ativadas ou desativadas no nível do locatário do Office 365. Com o Microsoft Teams ativado para um locatário, qualquer usuário que também esteja habilitado para o Microsoft Teams herdará as configurações do nível do locatário.

Segue abaixo a lista de recursos que o administrador do Office 365 pode escolher para habilitar ou desabilitar no Microsoft Teams.

A menos que esteja especificado, o valor padrão das opções é Ativado.

> [!NOTE]
> O administrador do Office 365 pode desativar o Microsoft Teams a qualquer momento no Centro de administração do Office 365. Esteja ciente de que os usuários com licenças ativas para o Microsoft Teams continuarão vendo o bloco do aplicativo mesmo que você o desative. Para obter detalhes sobre como remover licenças de usuários, consulte [Gerenciamento do acesso de usuários ao Microsoft Teams](user-access.md). Quando o Microsoft Teams é desabilitado, o acesso do cliente ao Microsoft Teams é bloqueado, mas os dados disponíveis por meio de outros clientes e serviços permanecem disponíveis, como arquivos via SharePoint e OneDrive. Todos os dados permanecem no lugar, a menos que as equipes sejam explicitamente excluídas.

<a name="office-365-tenant-wide-settings"></a>Configurações de todo o locatário do Office 365 
---------------------

Em **Configuração de todos os locatários**, você pode ativar e desativar opções em geral, integração de e-mails, aplicativos e armazenamento em nuvem personalizado.

Para editar as **Configurações de todo o locatário** do Microsoft Teams, acesse o Centro de administração do Office 365. Escolha **Configurações** > **Serviços e complementos** > **Microsoft Teams**.

### <a name="general"></a>Geral

A seção Geral permite que você defina as seguintes configurações para a sua organização:

> ![Captura de tela da seção Geral da Configuração de todos os locatários.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Mostrar organograma no perfil pessoal:** Quando essa configuração está ativada, é exibido o ícone do organograma no cartão de contato do usuário e, ao clicar, o organograma detalhado é exibido.

    ![Captura de tela do ícone do organograma no cartão de contato de um usuário.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Captura de tela de um organograma.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   **Usar o Skype for Business para destinatários que não têm o Microsoft Teams:** quando essa configuração está ativada, os usuários do Microsoft Teams podem entrar em contato com outros usuários da organização que não têm o Microsoft Teams ativado via Skype for Business.

-   **Permitir mensagens proativas de ajuda com T-bot:** quando essa configuração está ativada, o T-bot iniciará uma sessão de chat privado com os usuários para orientá-los sobre o uso do Microsoft Teams.

    ![Captura de tela da seção do T-Bot na interface do Microsoft Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>Integração de e-mails
-----------------

Ative esse recurso para que os usuários possam enviar emails para um canal no Microsoft Teams usando o endereço de email do canal. Os usuários podem fazer isso para qualquer canal pertencente a uma equipe que possuem. Os usuários também podem enviar e-mails para qualquer canal de uma equipe que tenha conectores adicionais habilitados para os membros da equipe. E, mesmo que um usuário não tenha permissão para criar um endereço de e-mail de canal, se alguém que tiver permissão criar esse endereço, o usuário poderá acessá-lo no menu do \<ícone de mais\> desse canal.

A seção de integração de e-mails permite que você defina as seguintes configurações para sua organização:

   ![Captura de tela da seção de Integração de e-mails da Configuração de todos os locatários.](media/QS-edu-email-integration.png)

-   **Permitir que os usuários enviem emails aos canais:** quando ativado, os ganchos de correio estão habilitados e os usuários podem postar mensagens em um canal enviando um email para o endereço de email do canal do Microsoft Teams.

> Para encontrar o endereço de e-mail do canal, clique em **Mais opções** ao lado do nome do canal, e então selecione **Obter endereço de e-mail**.

-   **Lista de remetentes restritos:** os domínios dos remetentes podem ser ainda mais limitados para garantir que somente os domínios SMTP permitidos possam enviar emails para os canais do Microsoft Teams.

<a name="apps"></a>Aplicativos
----

Os aplicativos do Microsoft Teams são uma ótima forma de integrar as ferramentas e os serviços importantes para a sua equipe diretamente em qualquer canal ou chat.

A seção **Aplicativos** permite que você defina as seguintes configurações para a sua organização:

![Captura de tela da seção de aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   **Permitir aplicativos externos no Microsoft Teams:** Quando ativado, os usuários podem adicionar guias e bots disponíveis ao locatário do Office 365.
![Captura de tela do controle de Permissão de aplicativos externos na seção Aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   **Permitir o carregamento lateral de aplicativos externos:** Quando ativado, os usuários podem instalar e habilitar bots e guias personalizadas.

<a name="custom-cloud-storage"></a>Armazenamento em nuvem personalizado
--------------------

No momento, as opções de armazenamento em nuvem do Microsoft Teams incluem Box, Dropbox, Google Drive e ShareFile. Os usuários podem carregar e compartilhar arquivos de serviços de armazenamento em nuvem nos canais e chats do Microsoft Teams. Clique ou toque no botão de alternância ao lado dos provedores de armazenamento em nuvem que a sua organização deseja usar.

![Captura de tela da seção de armazenamento em nuvem personalizado.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Configuração de usuários por licença
------------------------

Em **Configuração de usuários por licença**, você pode ativar e desativar opções de equipes e canais, chamadas e reuniões, e mensagens.

<a name="teams-and-channels"></a>Equipes e canais
------------------

Uma equipe foi designada a reunir um grupo de pessoas que trabalham em proximidade para realizar suas tarefas. As equipes podem ser dinâmicas para trabalhos baseado em projetos (por exemplo, lançamento de um produto ou criação d e uma sala de comando). Ou as equipes podem ser permanentes para refletir a estrutura interna da sua organização.

Como administrador, você pode gerenciar proprietários e membros da equipe usando o painel de Grupos no portal do centro de administração do Office 365. Na seção Equipes e canais, clique no link para **Usar o painel de Grupos no centro de administração do Office 365 para gerenciar equipes**.

Você pode controlar quais usuários da organização podem criar equipes no Microsoft Teams. As configurações de criação definidas pelos grupos do Office 365 se aplicam ao Microsoft Teams. Para obter mais informações sobre o gerenciamento de grupos do Office 365, veja [Criar grupos no Office 365](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) e [Controlar quem pode criar Grupos no Office 365](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

> [!NOTE]
> Não é possível criar equipes a partir do painel de Grupos. As equipes devem ser criadas usando o cliente de desktop ou o aplicativo Web do Microsoft Teams.

Por padrão, qualquer usuário pode criar uma equipe ou um grupo. Escolha **Equipes** à esquerda do cliente do Microsoft Teams (cliente de desktop ou aplicativo Web) e escolha **Criar e ingressar na equipe** na parte inferior do cliente, abaixo da lista de equipes.

Por padrão, o número máximo de equipes que um locatário do Office 365 pode ter atualmente é 500.000. Um administrador global pode criar um número ilimitado de equipes. Um usuário pode criar 250 equipes. Um proprietário de equipe pode incluir 2500 membros em uma equipe.

![Captura de tela da seção de configuração de usuários por licença.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Canais são subcategorias de equipes. Qualquer pessoa da equipe pode adicionar um canal e participar de conversas em um canal. Você pode criar um canal para uma atividade ou para um departamento. Conversas, arquivos e wikis são específicos para cada canal, mas todos os membros da equipe podem visualizá-los.

### <a name="calls-and-meetings"></a>Chamadas e reuniões

A seção **Chamadas e reuniões** permite que você defina as seguintes configurações para a sua organização:

> ![Captura de tela da seção de Chamadas e reuniões.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   **Permitir agendamento de reuniões privadas:** Quando ativado, os usuários podem agendar reuniões privadas que não estão listadas em nenhum canal.

-   **Permitir meetup de canais ad-hoc:**

-   **Permitir agendamento de reuniões de canais:** Quando ativado, os usuários podem agendar uma reunião para o canal em que todos os membros do canal podem entrar sem dificuldades com um só clique.

-   **Permitir vídeos em reuniões:** Especifica se o uso de vídeos é ou não permitido em reuniões.

-   **Permitir compartilhamento de tela em reuniões:** Especifica se o compartilhamento de tela é ou não permitido em reuniões.

-   **Permitir chamadas privadas:** Quando ativado, os usuários podem fazer chamadas privadas.

O número máximo de pessoas em uma reunião é 80. Pode haver 20 membros em um bate-papo privado, incluindo o usuário que o criou.

### <a name="messaging"></a>Mensagens 

A seção Mensagens permite que você defina as seguintes configurações para a sua organização:

![Captura de tela da seção de Mensagens.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Habilitar o Giphy para que os usuários possam adicionas gifs nas conversas:** Quando habilitado, os usuários podem usar imagens animadas nas conversas.

    -   **Classificação de conteúdo:** Quando as imagens animadas são ativadas, a classificação de conteúdo pode ser aplicada para restringir o tipo de imagens animadas que podem ser exibidas em conversas. As opções de classificação de conteúdo disponíveis são:

        -   Sem restrições

        -   Moderado (o valor padrão)

        -   Estrito

-   **Permitir memes que os usuários podem editar e adicionar às conversas:** Quando habilitado, os usuários podem usar memes da internet para fazer publicações bem humoradas.

-   **Permitir adesivos que os usuários podem editar e adicionar às conversas:** Quando habilitado, os usuários podem publicar imagens com texto editável para chamar a atenção dos membros do canal.

-   **Permitir que os usuários excluam todas as mensagens:** Quando habilitado, os proprietários do canal podem remover todas as mensagens de um canal.

-   **Permitir que os usuários editem suas próprias mensagens:** Quando habilitado, os usuários podem editar suas próprias mensagens.

-   **Permitir que os usuários excluam suas próprias mensagens:** Quando habilitado, os usuários podem excluir suas próprias mensagens.

-   **Permitir que os usuários batam papo de forma privada:** Quando habilitado, os usuários podem entrar em bate-papos privados que ficam visíveis apenas para as pessoas no bate-papo, e não para todos da equipe.


| |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Ponto de decisão         |Que configurações do Microsoft Teams a sua organização habilitará?         |
|![Ícone de próximos passos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Próximos passos        |Documente essas decisões na tabela [Atribuir funções e permissões no Microsoft Teams](assign-roles-permissions.md).         |

