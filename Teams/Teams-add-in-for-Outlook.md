---
title: Usar suplemento de Reunião do Microsoft Teams no Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 10/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: O Microsoft Teams instala um suplemento no Outlook para que os usuários possam agendar uma reunião do Teams pelo Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c0252d3bf8420711d67aec33aab1041cfe7eb1b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463128"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar o suplemento de Reunião do Teams no Outlook
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

O suplemento de Reunião do Teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013 ou o Office 2016 instalados em seus computadores Windows. Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook. 

![Captura de tela do suplemento do Teams na faixa de opções do Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Os usuários do Windows 7 devem instalar a [atualização para Universal C Runtime no Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para o suplemento de reunião de equipes trabalhem.

Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.

> [!NOTE]
> O suplemento de Reunião do Teams para o Outlook ainda não está disponível para usuários do Mac.

## <a name="authentication-requirements"></a>Requisitos de autenticação

O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna. Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook. Você pode corrigir isso da seguinte maneira:

- Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.
- Se a autenticação moderna estiver configurada, mas os usuários cancelaram a caixa de diálogo, você deverá instruí-los para entrar novamente usando a autenticação multifator.

Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar reuniões privadas

Permitir o agendamento para reuniões privadas deve ser habilitada no Centro de administração do Microsoft Teams para o plug-in obter implantado. No Centro de administração, vá para **reuniões** > **Políticas de reunião**e na seção **Geral** , alternar **Permitir o agendamento de reuniões privadas** para diante.)

![Captura de tela das configurações no Centro de administração do equipes da Microsoft.](media/teams-add-in-for-outlook-image1.png)

O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.

> [!NOTE]
> Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.

## <a name="other-considerations"></a>Outras considerações

O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:
- Alguns recursos de reunião online, como a gravação, a votação e o quadro de comunicações, ainda não estão disponíveis.
- As opções de reunião ainda não estão disponíveis.
- No momento, você pode apenas convidar pessoas da sua empresa, pois ainda não é possível o ingresso de usuários externos nas reuniões.
- O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal. As reuniões do canal devem ser agendadas dentro do Teams. Atualmente, o suplemento de Reunião do Teams no Outlook está disponível apenas para usuários do Windows, mas o suporte para Mac será disponibilizado em breve.
- O suplemento não funcionará se houver um proxy de autenticação no caminho de rede do computador do usuário e dos serviços do Teams.
- O add-in está sendo distribuído incrementalmente e pode não estar disponível para a sua organização ainda.

## <a name="troubleshooting"></a>Solução de problemas

Se você não conseguir a reunião de equipes suplemento para Outlook a fim de instalar, tente essas etapas de solução de problemas.

- Certifique-se de que tiverem sido aplicadas a todas as atualizações disponíveis para o cliente de desktop do Outlook 
- Reinicie o cliente de área de trabalho de equipes.
- Sair e entrar novamente para o cliente de desktop equipes.
- Reinicie o cliente de desktop do Outlook. (Certifique-se de que o Outlook não está em execução no modo de admin.)
- Verifique se que o nome da conta de usuário que fez logon não contém espaços. (Isso é um problema conhecido e será corrigido em uma atualização futura.)
- Certifique-se de logon único (SSO) está habilitado.

Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

