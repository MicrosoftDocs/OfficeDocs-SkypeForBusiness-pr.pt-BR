---
title: Obter clientes para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar as diversos clientes disponíveis para o Microsoft Teams, incluindo web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a24f4ba3c9470827c8a73bf8ac234cf7ae8467e8
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372784"
---
<a name="get-clients-for-microsoft-teams"></a>Obter clientes para o Microsoft Teams 
===========================

Microsoft Teams possui clientes móveis e disponíveis para a área de trabalho web (Windows e Mac), (Android, iOS e Windows Phone). Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.

<a name="desktop-client"></a>Cliente de desktop
--------------

> [!Tip]
> Assista a sessão de seguir para saber mais sobre os benefícios da área de trabalho do Windows, cliente, como planejar para ele e como implantá-la: [Equipes Windows Desktop Client](https://aka.ms/teams-clients)

O cliente de desktop do Microsoft Teams é um aplicativo autônomo e atualmente não faz parte do Office 365 ProPlus. As equipes está disponível para o Windows (7 +), versões de 32 bits e 64 bits e macOS (10.10 +). No Windows, equipes requer o .NET Framework 4.5 ou posterior; o instalador de equipes se oferecerá para instalá-lo se você não tiver a ele. 

Os clientes de área de trabalho oferecem suporte a comunicação em tempo real (áudio, vídeo e conteúdo compartilhamento) para reuniões de equipe, chamadas individuais chamando e particulares do grupo.

Clientes de área de trabalho podem ser baixados e instalados pelos usuários finais diretamente do [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se eles têm as permissões apropriadas de locais (direitos de administrador não são necessários para instalar o cliente de equipes em um PC, mas são necessários em um Mac).

Administradores de TI podem escolher seu método preferencial para distribuir os arquivos de instalação para computadores em sua organização, como o System Center Configuration Manager (Windows) ou Jamf Pro (macOS). Para obter o pacote MSI para distribuição do Windows, consulte [instalar equipes da Microsoft usando o MSI](msi-deployment.md).

> [!NOTE]
> A distribuição do cliente por esses mecanismos é apenas para a instalação inicial dos clientes Microsoft Teams, e não para atualizações futuras.

### <a name="windows"></a>Windows

A instalação do Microsoft Teams para Windows oferece instaladores para download nas arquiteturas de 32 bits e 64 bits.

> [!NOTE]
> A arquitetura (32 bits versus 64 bits) do Microsoft Teams é independente da arquitetura do Windows e do Office que está instalado.

O cliente Windows é implantado na pasta AppData localizada no perfil do usuário. A implantação no perfil local do usuário permite que o cliente seja instalado sem exigir direitos elevados. O cliente Windows aproveita os seguintes locais:

- % LocalAppData %\\Microsoft\\equipes

- % LocalAppData %\\Microsoft\\TeamsMeetingsAddin

- % AppData %\\Microsoft\\equipes

- % LocalAppData %\\SquirrelTemp

Quando os usuários iniciam uma chamada usando o cliente Microsoft Teams pela primeira vez, eles podem notar um aviso com as configurações de firewall do Windows, que solicita que os usuários permitam a comunicação. Os usuários podem ser instruídos para ignorar essa mensagem porque a chamada funcione, mesmo quando o aviso é descartado.

![Captura de tela de um diálogo do Alerta de Segurança do Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> A configuração do Firewall do Windows será alterada mesmo quando o aviso for descartado ao selecionar “Cancelar”. Serão criadas duas regras de entrada para teams.exe com a ação Block para protocolos TCP e UDP.

### <a name="mac"></a>Mac

Usuários de Mac podem instalar equipes usando um arquivo de instalação do pacote para computadores macOS. É obrigatório acesso administrativo para instalar o cliente Mac. O cliente macOS é instalado na pasta/aplicativos.

#### <a name="install-teams-by-using-the-pkg-file"></a>Instalar as equipes usando o arquivo de pacote

1. Na [página de download de equipes](https://teams.microsoft.com/downloads), **Mac**, clique em **Baixar**.
2. Clique duas vezes o arquivo de pacote.
3. Siga o Assistente de instalação para concluir a instalação.
4. Pasta/aplicativos equipes serão instaladas. É uma instalação de toda a máquina.

> [!NOTE]
> Durante a instalação, o pacote vai solicitar credenciais de administrador. O usuário precisa digitar as credenciais de administrador, independentemente de estarem ou não o usuário é um administrador.

Se um usuário atualmente tem uma instalação DMG das equipes e quiser substituí-la com a instalação do pacote, o usuário deve:

1. Saia do aplicativo de equipes.
2. Desinstale o aplicativo de equipes.
3. Instale o arquivo de pacote.

Administradores de TI podem usar implantação gerenciada de equipes para distribuir os arquivos de instalação para todos os Macs na sua organização, como Jamf Pro.

> [!NOTE]
> Se você perceber problemas ao instalar o pacote, fale conosco. Na seção **comentários** no final deste artigo, clique em **comentários sobre o produto**.

<a name="web-client"></a>Cliente web 
----------

O cliente da web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente de funcional completo que pode ser usado em uma variedade de navegadores. O cliente web oferece suporte a reuniões e chamadas usando webRTC, portanto, há não plug-in ou download necessário para executar as equipes em um navegador da web. O navegador deve ser configurado para permitir que os cookies de terceiros. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Cliente web executa a detecção de versão do navegador após a conexão com [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Se for detectada uma versão sem suporte do navegador, ela será bloqueie o acesso à interface da web e recomendável que o usuário baixe o cliente de área de trabalho ou aplicativos móveis.

<a name="mobile-clients"></a>Clientes móveis
--------------

Aplicativos móveis Microsoft Teams estão disponíveis para Android e iOS e são voltados para usuários no go participando de bate-papo com base em conversas e permitir que as chamadas de áudio ponto a ponto. Para aplicativos móveis, vá para o mobile relevante armazena Google tocar e loja de App Apple. O aplicativo do Windows Phone foi desativado 20 de julho de 2018 consulte [aqui](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) para obter mais informações.

As plataformas móveis suportadas para os aplicativos móveis da Microsoft Teams são as seguintes:

-   **Android**: 4.4 ou posterior

-   **iOS**: 10.0 ou posterior

> [!NOTE]
> A versão móvel deve estar disponível para o público na ordem para equipes trabalhem conforme o esperado.

Os aplicativos móveis são distribuídos e atualizados apenas pela respectiva loja de aplicativos da plataforma móvel e não estão disponíveis para ser distribuídos por meio de soluções MDM (gerenciamento de dispositivos móveis) ou carregamento lateral.


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Get_clients_for_Microsoft_Teams_image4.png)      |Ponto de decisão         |Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?         |
|![Ícone de próximos passos.](media/Get_clients_for_Microsoft_Teams_image5.png)     |Próximos passos         |Se sua organização restringe a instalação de software, verifique se esse processo é compatível com o Microsoft Teams. Nota: Os direitos de administrador não são obrigatórios para a instalação do cliente PC, mas são obrigatórios para a instalação em Mac.         |


  <span id="_Hlk477176062" class="anchor"></span>  Ponto de decisão  Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?

<a name="client-update-management"></a>Gerenciamento de atualização do cliente
------------------------

No momento, os clientes são atualizados automaticamente pelo serviço do Microsoft Teams, sem a necessidade de intervenção de um administrador de TI. Se uma atualização estiver disponível, o cliente baixará automaticamente a atualização e, quando o aplicativo estiver ocioso por um período de tempo, o processo de atualização será iniciado.

<a name="client-side-configurations"></a>Configurações do lado do cliente
---------------------------

No momento, não estão disponibilizadas opções para configurar o cliente através do administrador do locatário, do PowerShell, do Group Policy Objects, nem do registro.

<a name="notification-settings"></a>Configurações de notificação
----------------------------

No momento, não estão disponibilizadas opções para administradores de TI definirem as configurações de notificação do lado do cliente. Todas as opções de notificação são definidas pelo usuário. A figura abaixo descreve as configurações padrão do cliente.

![Captura de tela das configurações de notificação.](media/Get_clients_for_Microsoft_Teams_image6.png)
