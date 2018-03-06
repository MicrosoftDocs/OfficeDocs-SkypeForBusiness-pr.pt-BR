---
title: Obter clientes para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "Saiba como usar as diversos clientes disponíveis para o Microsoft Teams, incluindo web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone)."
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f2208ed21eb2db33f8d8ff90af97caa5b4912dfd
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="get-clients-for-microsoft-teams"></a>Obter clientes para o Microsoft Teams 
===========================

O Microsoft Teams tem clientes disponíveis para web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone). Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.

<a name="web-client"></a>Cliente web 
----------------

O cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente completo e funcional que pode ser usado em uma grande variedade de navegadores. Neste ponto, o cliente Web não dá suporte à comunicação em tempo real (ou seja, entrar em reuniões e receber chamadas individuais). O navegador também precisa ser configurado para permitir cookies de terceiros. 

Não é necessário nenhum plug-in ou download para utilizar o Microsoft Teams em um navegador da Web.

O cliente web executa a detecção da versão do navegador ao se conectar a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) e se for detectada uma versão de navegador não suportada, o acesso à interface web será bloqueada, e a recomendação é que o usuário baixe o cliente desktop ou o aplicativo móvel.

<a name="internet-browser-support"></a>Suporte a navegadores da Internet
------------------------------
O Teams dá suporte aos seguintes navegadores da Internet: 
- Internet Explorer 11
- Microsoft Edge
- A versão mais recente do Chrome, além de duas versões anteriores
- A versão mais recente do Firefox, além de duas versões anteriores

> [!NOTE]
> No momento, não há suporte para o Safari. Confira no [Roteiro do Microsoft Teams](http://aka.ms/TeamsRoadmap) as notícias sobre novos recursos do Microsoft Teams. Os usuários que tentarem abrir o Microsoft Teams no Safari serão direcionados para baixar o cliente de desktop do Microsoft Teams.

<a name="desktop-clients"></a>Clientes desktop
------------------------

O cliente desktop do Microsoft Teams é um aplicativo autônomo que, no momento, não faz parte do Office Pro Plus. O Microsoft Teams está disponível para Windows (7+), ambas as versões de 32 bits e 64 bits, e para MacOS (10.10+).

Os clientes desktop tem suporte para comunicação em tempo real (áudio, vídeo e compartilhamento de conteúdo) para reuniões de equipe, chamadas em grupo e chamadas privadas individuais.

Os clientes desktop podem ser baixados e instalados por usuários final diretamente de [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se tiverem as permissões locais apropriadas (os direitos de administrador não são obrigatórios para instalar o cliente Teams em um PC, mas são obrigatórios para Mac).

Os administradores de TI podem escolher seu método preferido para distribuir os arquivos de instalação para as máquinas da sua organização, como o System Center Configuration Manager (Windows) ou o Casper Suite (MacOS).



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
