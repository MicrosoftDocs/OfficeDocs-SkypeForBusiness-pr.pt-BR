---
title: Gerenciar recursos de Teams da Microsoft em sua organização do Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como ativar ou desativar apps Teams da Microsoft em sua organização do Office 365, incluindo guias, conectores, bots ou qualquer combinação dos três.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f78876064ae50221562bd42b334545f627a02fb
ms.sourcegitcommit: 9138325ba2652a9ee3602d259de811082080e358
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842072"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Gerenciar recursos de Teams da Microsoft em sua organização do Office 365

Todas as definições de equipes em breve serão migradas para o novo Teams Microsoft & Skype para Business Admin Center. O único recurso de equipes que é gerenciado no Centro de administração do Office 365 é Apps. 

Salvo indicação em contrário, o valor padrão para uma opção é **no**.

## <a name="office-365-tenant-wide-settings"></a>Configurações de todo o locatário do Office 365 

Nas **configurações de todo o locatário**, você pode ativar ou desativar aplicativos.

Para editar **as configurações de todo o locatário** para equipes, vá para o Microsoft Teams & Skype para Business Admin Center e selecione **portal herdada**. Escolha **Configurações** > **Serviços e complementos** > **Microsoft Teams**. Se você tiver entrado como administrador do Office 365, este link deverá direcioná-lo corretamente: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Aplicativos

Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros. Existem políticas de administração do Teams que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos. Essas diretivas permitem especificar quais aplicativos são permitidos e não permitidos, novo comportamento de aplicativo externo, e se os aplicativos do lado do carregamento é permitido. 

Em **Aplicativos**, você pode definir estas configurações para a sua organização: 

![Captura de tela da seção de aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Allow external apps in Microsoft Teams** (Permitir aplicativos externos no Microsoft Teams): quando essa opção está ativada, os usuários podem adicionar guias e bots disponíveis para o locatário do Office 365. 
 
    ![Captura de tela do controle de permissão de aplicativos externos na seção Aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Enable new external apps by default** (Habilitar novos aplicativos externos por padrão): quando essa opção está ativada, os usuários podem ativar novos aplicativos assim que eles são adicionados ao catálogo de aplicativos do Teams. Desative essa opção para poder controlar os novos aplicativos. Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas. 

- **Permitir sideloading de aplicativos externos**: quando essa opção estiver ativada, os usuários podem instalar e ativar bots personalizados e guias. 

Para saber mais, leia [Configurações de administração para aplicativos no Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Configurações de toda a organização de equipes

Você pode controlar as configurações de usuário de toda a organização no Microsoft Teams & Skype para Business Admin Center. Para editar as configurações de toda a organização, vá para o Microsoft Skype para Business Admin Center e, em seguida, selecione **configurações de toda a organização**. Você pode configurar as configurações a seguir.

### <a name="external-access"></a>Acesso externo

**Acesso externo** permite que suas equipes e Skype para usuários empresariais se comunicar com usuários que estão fora da sua organização. Para configurar o acesso externo, vá para [Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização equipes](let-your-teams-users-communicate-with-other-people.md).

### <a name="guest-access"></a>Acesso de convidados

**Acesso de convidado** no Microsoft Teams permite que as equipes em sua organização para colaborar com pessoas fora da sua organização, concedendo a eles acesso às equipes e canais. Qualquer pessoa com uma conta de email de consumidor ou de negócios, como o Outlook, Gmail ou outras pessoas, pode participar como um convidado em equipes com acesso completo à equipe chats, reuniões e arquivos. Para obter mais informações, consulte [acesso de convidado em equipes da Microsoft](guest-access.md).

### <a name="teams-settings"></a>Configurações de equipes

Nas **configurações de equipes**, você pode configurar integração de email, opções de armazenamento de nuvem, Skype para interoperabilidade de negócios e dispositivos.

#### <a name="email-integration"></a>Integração de e-mails

Ative esse recurso para que os usuários possam enviar emails para um canal no Microsoft Teams usando o endereço de email do canal. Os usuários podem fazer isso para qualquer canal pertencente a uma equipe que possuem. Os usuários também podem enviar emails a qualquer canal em uma equipe que possui a adição de conectores ativada para que membros da equipe. Para ativar a integração de email, certifique-se de que **Permitir que os usuários para enviar emails para um endereço de email do canal** está **ativado**. 

#### <a name="files"></a>Arquivos

Aqui você pode ativar ou desativar opções de armazenamento de arquivo de nuvem e de compartilhamento de arquivo. 

Os usuários podem carregar e compartilhar arquivos de serviços de armazenamento em nuvem nos canais e chats do Microsoft Teams. Opções de armazenamento de nuvem em equipes atualmente incluem ShareFile, pasta de recados, caixa e Google unidade. Ative a opção para os provedores de armazenamento em nuvem que sua organização deseja usar.

#### <a name="organization"></a>Organização

Aqui você pode ativar a guia de **organização** , que mostra o gráfico organizacional detalhado para a organização do usuário. Para obter mais informações, consulte [Use a guia organização em equipes](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="skype-for-business-interop"></a>Skype para interoperabilidade de negócios

Use esta configuração para permitir que equipes usuários bate-papo com Skype para usuários comerciais. Para obter informações detalhadas sobre a interoperabilidade entre equipes e Skype para os negócios, vá para [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="devices"></a>Dispositivos

Essas configurações controlam o comportamento de conta do recurso para dispositivos do Hub de superfície participando de reuniões Teams da Microsoft. Use estas configurações para configurar os requisitos de autenticação, exigem um PIN de conteúdo e ativar contas de recurso do Hub de superfície para enviar mensagens.

- **Exigir um formulário secundário de autenticação para acessar o conteúdo da reunião** – selecione o nível de acesso que os usuários têm quando inserem o conteúdo FIXAR.
- **Definir o PIN de conteúdo** – exigir que os usuários insiram esse PIN para impedir o acesso não autorizado a documentos. Isso impede que um usuário não autorizado ingressando futuras reuniões e anexos de navegação.
- **Contas de recursos podem enviar mensagens** – ativar esta configuração **em** para permitir que as mensagens sejam enviadas da conta de recurso do Hub de superfície.

#### <a name="search"></a>Pesquisar

Pesquisa de diretório com escopo de Teams da Microsoft usa a política de catálogo de endereços do Exchange (APB) para permitir que as organizações a criar limites virtuais que controlam como os usuários podem localizar e se comunicar com outros usuários em suas organizações. Você pode querer usar uma pesquisa de diretório com escopo em situações como essas:

- Sua organização tem várias empresas dentro de seu locatário que você deseja manter separados. 
- Sua escola deseja limitar chats entre professores e alunos. 

Alterne esta configuração **na** ativem pesquisas de diretório com escopo.

### <a name="teams-upgrade"></a>Atualização de equipes

Você pode usar essas configurações para configurar como os usuários serão atualizados do Skype para negócios a Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modo de coexistência
Você pode especificar um modo de coexistência: **somente equipes**, **Ilhas** (equipes e Skype para vão de negócios coexistir) ou **Skype para negócios apenas**. O modo de coexistência escolhido determina o roteamento de chamadas de entrada e bate-papos e o aplicativo que é usado pelo usuário para iniciar o bate-papos e chamadas ou agendar reuniões. Para obter mais informações sobre modos de coexistência, vá para [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferências do aplicativo

Aqui, você pode escolher o aplicativo que os usuários utilizarão para ingressar Skype para negócios reuniões (Skype para o [Aplicativo do Skype reuniões](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)ou comercial). Essa configuração não é dependente da configuração do modo de coexistência.


