---
title: Usar suplemento de Reunião do Microsoft Teams no Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 05/29/2019
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
ms.openlocfilehash: 51d28bc5806aebdad1bb83bb08945f45d505cde9
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35203930"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar o suplemento de Reunião do Teams no Outlook
=======================================

O suplemento de reunião do teams permite aos usuários agendar uma reunião do teams a partir do Outlook. O suplemento está disponível para o Outlook no Windows, Mac, Web e celular.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Suplemento de reunião do teams no Outlook para Windows

O suplemento de reunião do teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2010, o Office 2013 ou o Office 2016 instalado no computador Windows. Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook.

![Captura de tela do suplemento de reunião do teams na faixa de opções do Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.
> - Os usuários do Windows 7 devem instalar a [atualização do tempo de execução universal C no Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) no Windows para que o suplemento de reunião do teams funcione.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Suplemento de reunião do teams no Outlook para Mac

O botão de reunião do teams no Outlook para Mac aparecerá na faixa de opções do Outlook para Mac se o Outlook estiver executando o Build de produção 16.24.414.0 e posterior.

As coordenadas da reunião (as equipes que ingressam em links de discagem e números de discagem) serão adicionadas ao convite de reunião após o usuário clicar em **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Suplemento de reunião do teams no Outlook Web App

O botão reuniões do teams no Outlook Web App será exibido como parte da criação do novo evento se o usuário estiver em uma versão anterior do novo Outlook na Web. Consulte o [blog do Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) para saber como os usuários podem experimentar a versão anterior do novo Outlook na Web.

![Captura de tela do suplemento de reunião do teams no Outlook Web App](media/teams-meeting-add-in-web.png)

As coordenadas da reunião (as equipes que ingressam em links de discagem e números de discagem) serão adicionadas ao convite de reunião após o usuário clicar em **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Suplemento de reunião do teams no Outlook Mobile (iOS e Android)

O botão de reunião do teams é exibido nas versões mais recentes do iOS e do aplicativo Android do Outlook.

![Captura de tela do suplemento de reunião do teams no Outlook Mobile](media/teams-meeting-add-in-mobile.png)

As coordenadas da reunião (as equipes que ingressam em links de discagem e números de discagem) serão adicionadas ao convite de reunião após o usuário clicar em **Enviar**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Suplemento de reunião do Microsoft Teams e localizar no Outlook
Findtime é um suplemento do Outlook que ajuda os usuários a alcançar um consenso em um horário de reunião entre as empresas. Depois que os convidados da reunião tiverem fornecido seus horários preferenciais, o Findtime envia o convite de reunião para o nome do usuário. Se a opção de **reunião online** for selecionada em findtime, localizartime agendará uma reunião do Skype for Business ou do Microsoft Teams. (Localizartime usará o que tiver sido definido por sua organização como o canal de reunião online padrão.)

> [!NOTE]  
> Se você salvou uma configuração do Skype for Business no [painel findtime](https://findtime.microsoft.com/UserDashboard), findtime usará isso em vez do Microsoft Teams. Se você quiser usar o Microsoft Teams, exclua a configuração do Skype for Business no painel.

Consulte [agendar reuniões com](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) o findtime para obter mais informações.

## <a name="authentication-requirements"></a>Requisitos de autenticação

O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna. Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook. Você pode corrigir isso da seguinte maneira:

- Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.
- Se a autenticação moderna estiver configurada, mas cancelada na caixa de diálogo, você deverá instruir os usuários a entrar novamente usando a autenticação multifator.

Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar reuniões privadas

**Permitir agendamento de reuniões particulares** deve estar habilitado no centro de administração do Microsoft Teams para que o suplemento seja implantado. No centro de administração, vá para **Reuniões** > **Políticas de Reunião**, e na seção **Geral**, ative **Permitir agendamento de reuniões particulares** para Ativado.)

![Captura de tela das configurações no centro de administração do Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.

> [!NOTE]
> Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Política de atualização do Teams e suplemento de reunião do teams para Outlook

Os clientes podem [escolher a jornada da atualização do Skype for Business para](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)o Teams. Os administradores de locatários podem usar o modo de coexistência de equipes para definir essa jornada para seus usuários. Os administradores de locatários têm a opção de permitir que os usuários usem equipes junto com o Skype for Business (modo de ilhas). 

Quando os usuários que estão no modo ilha agendam uma reunião no Outlook, normalmente esperam poder escolher se deseja agendar uma reunião do Skype for Business ou de uma reunião do teams. No Outlook na Web, no Outlook no Outlook e no Outlook Mac, os usuários visualizam os suplementos do Skype for Business e do teams quando estiverem no modo de ilhas. Devido a determinadas limitações na versão inicial, o Outlook Mobile só pode dar suporte à criação de reuniões do Skype for Business **ou** do teams. Consulte a tabela a seguir para obter detalhes.

| Modo de coexistência no centro de administração do teams | Provedor de reuniões padrão no Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| McDonald | Skype for Business |
| Somente Skype for Business | Skype for Business |
| Skype for Business com colaboração em equipe | Skype for Business |
| Skype for Business com colaboração e reuniões do teams | Microsoft Teams |
| Somente equipes | Microsoft Teams |

## <a name="other-considerations"></a>Outras considerações

O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:

- O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal. As reuniões do canal devem ser agendadas dentro do Teams.
- O suplemento não funcionará se houver um proxy de autenticação no caminho de rede do computador do usuário e dos serviços do Teams.
- Os usuários não podem agendar eventos dinâmicos no Outlook. Acesse o Teams para agendar eventos dinâmicos. Para obter mais informações, consulte [o que são eventos do Microsoft Teams Live?](teams-live-events/what-are-teams-live-events.md).

## <a name="troubleshooting"></a>Solução de problemas

Se você não conseguir instalar o suplemento Teams Meeting para o Outlook, tente estas etapas de solução de problemas.

- Verifique se todas as atualizações disponíveis para o cliente da área de trabalho do Outlook foram aplicadas.
- Reinicie o cliente de área de trabalho do Teams.
- Saia e entre novamente no cliente de área de trabalho do Teams.
- Reinicie o cliente para área de trabalho do Outlook. (Certifique-se de que o Outlook não esteja sendo executado no modo de administrador.)
- Certifique-se de que o nome da conta do usuário que efetuou logon não contenha espaços. (Esse é um problema conhecido e será corrigido em uma atualização futura.)
- Certifique-se de que o logon único (SSO) esteja ativado.

Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
