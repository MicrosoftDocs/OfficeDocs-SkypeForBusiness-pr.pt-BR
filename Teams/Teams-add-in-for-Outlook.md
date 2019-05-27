---
title: Usar suplemento de Reunião do Microsoft Teams no Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
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
ms.openlocfilehash: 801c4f43e9aafa7fe8331d85b601afd584505164
ms.sourcegitcommit: e5cb24ad166268392e692d3d1b92125646e5d66e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "34417439"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar o suplemento de Reunião do Teams no Outlook
=======================================

O suplemento de Reunião do Teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013 ou o Office 2016 instalados em seus computadores Windows. Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook. 

![Captura de tela do suplemento do Teams na faixa de opções do Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Os usuários do Windows 7 devem instalar a [atualização para o Universal C Runtime no Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para que o suplemento de Reunião do Teams funcione.

Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.

> [!NOTE]
> O botão reunião do teams no Outlook para Mac aparecerá na faixa de opções do Outlook para Mac se o Outlook estiver executando o Build de produção 16,20 e posterior.

## <a name="authentication-requirements"></a>Requisitos de autenticação

O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna. Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook. Você pode corrigir isso da seguinte maneira:

- Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.
- Se a autenticação moderna estiver configurada, mas os usuários cancelaram a caixa de diálogo, você deverá instruí-los para entrar novamente usando a autenticação multifator.

Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar reuniões privadas

**Permitir agendamento de reuniões particulares** deve estar habilitado no centro de administração do Microsoft Teams para que o plug-in seja implantado. No centro de administração, vá para **Reuniões** > **Políticas de Reunião**, e na seção **Geral**, ative **Permitir agendamento de reuniões particulares** para Ativado.)

![Captura de tela das configurações no centro de administração do Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.

> [!NOTE]
> Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.

## <a name="other-considerations"></a>Outras considerações

O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:
- A sondagem ainda não está disponível.
- O quadro de comunicações está começando a ser revertido.
- As opções de reunião ainda não estão disponíveis.
- No momento, você pode apenas convidar pessoas da sua empresa, pois ainda não é possível o ingresso de usuários externos nas reuniões.
- O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal. As reuniões do canal devem ser agendadas dentro do Teams. Atualmente, o suplemento de Reunião do Teams no Outlook está disponível apenas para usuários do Windows, mas o suporte para Mac será disponibilizado em breve.
- O suplemento não funcionará se houver um proxy de autenticação no caminho de rede do computador do usuário e dos serviços do Teams.
- O suplemento está sendo implementado de forma incremental e pode não estar disponível para sua organização ainda.

## <a name="troubleshooting"></a>Solução de problemas

Se você não conseguir instalar o suplemento Teams Meeting para o Outlook, tente estas etapas de solução de problemas.

- Garantir que todas as atualizações disponíveis para o cliente de Outlook desktop tenham sido aplicadas 
- Reinicie o cliente de área de trabalho do Teams.
- Saia e entre novamente no cliente de área de trabalho do Teams.
- Reinicie o cliente para área de trabalho do Outlook. (Certifique-se de que o Outlook não esteja sendo executado no modo de administrador.)
- Certifique-se de que o nome da conta do usuário que efetuou logon não contenha espaços. (Esse é um problema conhecido e será corrigido em uma atualização futura.)
- Certifique-se de que o logon único (SSO) esteja ativado.

Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

