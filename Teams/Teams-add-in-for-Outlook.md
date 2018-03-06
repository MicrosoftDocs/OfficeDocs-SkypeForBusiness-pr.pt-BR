---
title: "Usar suplemento de Reunião do Microsoft Teams no Outlook"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "O Microsoft Teams instala um suplemento no Outlook para que os usuários possam agendar uma reunião do Teams pelo Outlook."
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2fb35e720d100e6bb2130fbacf16197397f201c
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar o suplemento de Reunião do Teams no Outlook
=======================================

O suplemento de Reunião do Teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013 ou o Office 2016 instalados em seus computadores Windows. Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook. 

![Captura de tela do suplemento do Teams na faixa de opções do Outlook.](media/Teams-add-in-for-Outlook.png)

Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.

> [!NOTE]
> O suplemento de Reunião do Teams para o Outlook ainda não está disponível para usuários do Mac.

## <a name="authentication-requirements"></a>Requisitos de autenticação

O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna. Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook. Você pode corrigir isso da seguinte maneira:

- Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.
- Se a autenticação moderna estiver configurada, mas os usuários cancelaram a caixa de diálogo, você deverá instruí-los para entrar novamente usando a autenticação multifator.

Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar reuniões privadas

A permissão de agendamento de reuniões privadas deve ser habilitada no [Centro de administração do Office 365](https://portal.office.com/adminportal/home) para que o plug-in seja implantado.

![Captura de tela das configurações da seção Chamadas e reuniões do Centro de administração do Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

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

Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

