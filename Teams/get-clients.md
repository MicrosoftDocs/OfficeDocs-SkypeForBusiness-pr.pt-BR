---
title: Obter clientes para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
localization_priority: Normal
description: Saiba como usar as diversos clientes disponíveis para o Microsoft Teams, incluindo web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61bfc43321433a06eba8196b732f8f12dded0d8d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
<a name="get-clients-for-microsoft-teams"></a>Obter clientes para o Microsoft Teams 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

O Microsoft Teams tem clientes disponíveis para web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone). Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.

<a name="web-client"></a>Cliente web 
----------

O cliente da web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente de funcional completo que pode ser usado em uma variedade de navegadores. O cliente web oferece suporte a reuniões e chamadas usando webRTC, portanto, há não plug-in ou download necessário para executar as equipes em um navegador da web. O navegador deve ser configurado para permitir que os cookies de terceiros. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Cliente web executa a detecção de versão do navegador após a conexão com [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) e se uma versão sem suporte do navegador é detectada, ela será bloqueie o acesso à interface da web e recomendável que o usuário baixe o cliente de área de trabalho ou aplicativos móveis.

<a name="desktop-client"></a>Cliente de desktop
--------------

O cliente de desktop do Microsoft Teams é um aplicativo autônomo e atualmente não faz parte do Office Pro Plus. As equipes está disponível para o Windows (7 +), versões de 32 bits e 64 bits e MacOS (10.10 +). No Windows, equipes requer o .NET framework 4.5 ou posterior; o instalador de equipes se oferecerá para instalá-lo se você não tiver a ele. 

Os clientes de área de trabalho oferecem suporte a comunicação em tempo real (áudio, vídeo e conteúdo compartilhamento) para reuniões de equipe, chamadas individuais chamando e particulares do grupo.

Clientes de área de trabalho podem ser baixados e instalados pelos usuários finais diretamente do [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se eles têm as permissões apropriadas de locais (direitos de administrador não são necessários para instalar o cliente de equipes em um PC, mas são necessários em um Mac).

Os administradores de TI podem escolher seu método preferido para distribuir os arquivos de instalação para as máquinas da sua organização, como o System Center Configuration Manager (Windows) ou o Casper Suite (MacOS). Para fazer a distribuição de pacote do MSI para Windows, consulte [instalar equipes da Microsoft usando o MSI](msi-deployment.md).

> [!NOTE]
> A distribuição do cliente por esses mecanismos é apenas para a instalação inicial dos clientes Microsoft Teams, e não para atualizações futuras.


#### <a name="windows"></a>Windows

A instalação do Microsoft Teams para Windows oferece instaladores para download nas arquiteturas de 32 bits e 64 bits. A arquitetura deve corresponder àquela do sistema operacional, a qual for o padrão do download online.



> [!NOTE]
> A arquitetura (32 bits x 64 bits) do Microsoft Teams é independente da arquitetura do Office que está instalado.

O cliente Windows é implantado na pasta AppData localizada no perfil do usuário. A implantação no perfil local do usuário permite que o cliente seja instalado sem exigir direitos elevados. O cliente Windows é instalado nos seguintes locais:

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

Quando os usuários iniciam uma chamada usando o cliente Microsoft Teams pela primeira vez, eles podem notar um aviso com as configurações de firewall do Windows, que solicita que os usuários permitam a comunicação. Os usuários podem ser instruídos a ignorar essa mensagem porque a chamada funcionará, mesmo quando o aviso for descartado.

![Captura de tela de um diálogo do Alerta de Segurança do Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> A configuração do Firewall do Windows será alterada mesmo quando o aviso for descartado ao selecionar “Cancelar”. Serão criadas duas regras de entrada para teams.exe com a ação Block para protocolos TCP e UDP.

#### <a name="mac"></a>Mac

A Microsoft também fornece um arquivo de instalação DMG para computadores Mac OSX. É obrigatório acesso administrativo para instalar o cliente Mac. O cliente Mac OSX é instalado na pasta /Applications.


<a name="mobile-clients"></a>Clientes móveis
--------------

Os aplicativos móveis do Microsoft Teams estão disponíveis para Android, iOS e Windows Phone, estão voltados para usuários participando de conversas baseadas em bate-papo em qualquer lugar, e permitem chamadas de áudio ponto a ponto. Para aplicativos móveis, acesse a respectiva loja de aplicativos Google Play, Apple App Store ou Microsoft Store.

As plataformas móveis suportadas para os aplicativos móveis da Microsoft Teams são as seguintes:

-   **Android**: 4.4 ou posterior

-   **iOS**: 10.0 ou posterior

-   **Windows Phone**: Windows 10 Mobile

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
