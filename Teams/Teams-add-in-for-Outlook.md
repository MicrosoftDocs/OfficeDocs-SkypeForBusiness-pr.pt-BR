---
title: Usar suplemento de Reunião do Microsoft Teams no Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: O Microsoft Teams instala um suplemento no Outlook para que os usuários possam agendar uma reunião do Teams pelo Outlook.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89e7db133b8878e77dbf14025b97c658b0de21e4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349605"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar o suplemento de Reunião do Teams no Outlook
=======================================

O suplemento de reunião do Teams permite que os usuários agendem uma reunião do Teams no Outlook. O suplemento está disponível para o Outlook no Windows, Mac, Web e dispositivos móveis.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Suplemento de reunião do Teams no Outlook para Windows

O suplemento de reunião do teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013, o Office 2016 ou o Office 2019 instalado no computador Windows. Os usuários verão o suplemento de reunião do Teams na faixa de opções Calendário do Outlook.

![Captura de tela do suplemento de reunião do Teams na faixa de opções do Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Há mais considerações se a sua organização executar tanto o Skype for Business Teams quanto o Skype for Business. Em algumas circunstâncias, o suplemento Teams não está disponível no Outlook. Confira [a atualização do Skype for Business para o Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) para obter detalhes.
> - Ter permissões do usuário para executar o arquivo Regsvr32.exe é um requisito mínimo para que o suplemento Reunião do Teams seja instalado no computador.
> - Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.
> - Se você estiver usando uma instalação do Outlook do Office da Microsoft Store, não haverá suporte para o suplemento Reunião do Teams. Os usuários que precisam desse suplemento são aconselhados a instalar a versão Click-to-Run do Office, conforme descrito no artigo [Office no Windows 10 no modo S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Suplemento de reunião do Teams no Outlook para Mac

O botão reunião do teams no Outlook para Mac será exibido na faixa de opções do Outlook para Mac se o Outlook estiver executando o Build Build 16.24.414.0 e posterior e estiver ativado com uma assinatura do Microsoft 365 ou do Office 365 Client.

As coordenadas da reunião (os números de discagem e de ingresso no Teams) serão adicionadas ao convite da reunião depois que o usuário clicar em **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Suplemento de reunião do Teams no Outlook Web App

O botão Reunião do Teams no Outlook Web App aparecerá como parte da criação de um novo evento se o usuário estiver em uma versão anterior do novo Outlook na Web. Consulte o [Blog do Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) para saber como os usuários podem experimentar a versão inicial do novo Outlook na Web.

![Captura de tela do suplemento de reunião do Teams no Outlook Web App](media/teams-meeting-add-in-web.png)

As coordenadas da reunião (os números de discagem e de ingresso no Teams) serão adicionadas ao convite da reunião depois que o usuário clicar em **Enviar**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Suplemento de reunião do Teams no Outlook para dispositivos móveis (iOS e Android)

O botão Reunião do Teams é exibido nas versões mais recentes do aplicativo do Outlook para iOS e Android.

![Captura de tela do suplemento Reunião do Teams no Outlook mobile](media/teams-meeting-add-in-mobile.png)

As coordenadas da reunião (os números de discagem e de ingresso no Teams) serão adicionadas ao convite da reunião depois que o usuário clicar em **Enviar**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Suplemento de reunião do Teams e Verificador de Horas para o Outlook
Findtime é um suplemento do Outlook que ajuda os usuários a alcançarem um consenso em um horário de reunião entre as empresas. Depois que os convidados da reunião fornecem seu horário preferido, o Verificador de Horas envia o convite da reunião em nome do usuário. Se a opção **Reunião online** estiver selecionada no Verificador de Horas, o Verificador de Horas agendará uma reunião do Skype for Business ou Microsoft Teams. (O Verificador de Horas usará o que tiver sido definido pela sua organização como o canal de reunião online padrão.)

> [!NOTE]  
> Se você salvou uma configuração do Skype for Business no [painel do Verificador de Horas](https://findtime.microsoft.com/UserDashboard), o Verificador de Horas usará essa configuração em vez do Microsoft Teams. Se você deseja usar o Microsoft Teams, exclua a configuração do Skype for Business no seu painel.

Para obter mais informações, consulte [agendar reuniões com o findtime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Requisitos de autenticação

O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna. Se os usuários não usarem esse método para se conectar, ainda poderão usar o cliente do Teams, mas não será possível agendar reuniões online do teams usando o suplemento do Outlook. Você pode corrigir isso da seguinte maneira:

- Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.
- Se a Autenticação Moderna estiver configurada, mas os usuários tiverem cancelado a mesma na caixa de diálogo, você deve instruir os usuários a entrarem novamente usando a autenticação multifator.

Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar reuniões privadas

A **permissão para agendar reuniões privadas** deve estar ativada no centro de administração do Microsoft Teams para que o suplemento seja implantado. No centro de administração, vá para **Reuniões** > **Políticas de Reunião**, e na seção **Geral**, ative **Permitir agendamento de reuniões particulares** para Ativado.)

![Captura de tela das configurações no centro de administração do Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.

> [!NOTE]
> Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Diretiva de atualização do Teams e o suplemento de reunião do Teams para Outlook

Os clientes podem [escolher sua jornada de atualização do Skype for Business para o Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Os administradores de locatários podem usar o modo de coexistência do Teams para definir essa jornada para seus usuários. Os administradores de locatários têm a opção de permitir que os usuários usem o Teams juntamente ao Skype for Business (modo Ilhas). 

Quando os usuários que estão no modo Ilha agendam uma reunião no Outlook, eles normalmente esperam poder escolher agendar uma reunião do Skype for Business ou do Teams. No Outlook na Web, Outlook para Windows e Outlook para Mac, os usuários veem tanto o suplemento do Skype for Business como o do Teams quando estão no modo Ilhas. Devido a certas limitações na versão inicial, o Outlook mobile pode oferecer suporte apenas à criação de reuniões do Skype for Business **ou** do Teams. Veja a tabela a seguir para obter detalhes.

| Modo de coexistência no centro de administração do Teams | Provedor de reuniões padrão no Outlook mobile |
| --------------------------------------|---------------------------------------------|
| Ilhas | Skype for Business |
| Somente Skype for Business | Skype for Business |
| Colaboração do Skype for Business com o Teams | Skype for Business |
| Colaboração e reuniões do Skype for Business com o Teams | Teams |
| Somente Teams | Teams |

## <a name="other-considerations"></a>Outras considerações

O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:

- O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal. As reuniões do canal devem ser agendadas dentro do Teams.
- O suplemento não funcionará se um proxy de autenticação estiver no caminho de rede do computador do usuário e dos serviços do teams.
- Os usuários não podem agendar eventos ao vivo no Outlook. Vá para o Teams para agendar eventos ao vivo. Para obter mais informações, consulte [O que são eventos ao vivo do Microsoft Teams?](teams-live-events/what-are-teams-live-events.md).

Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="troubleshooting"></a>Solução de problemas

Use as etapas a seguir para solucionar problemas com o suplemento de reunião do teams.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>O suplemento de reunião do Microsoft Teams no Outlook para Windows não é mostrado

Se você não conseguir instalar o suplemento Teams Meeting para o Outlook, tente estas etapas de solução de problemas.

- Os usuários do Windows 7 devem instalar a [atualização para o Universal C Runtime no Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para que o suplemento de Reunião do Teams funcione.
- Verifique se o usuário tem uma política de atualização do teams que permite agendar reuniões no Teams. Para obter mais detalhes, confira [a atualização do Skype for Business para o Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
- Verifique se o usuário tem uma política de reunião do teams que permite o suplemento do Outlook. Consulte [gerenciar políticas de reunião no Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) para obter mais detalhes.
- Verifique se o usuário tem o cliente da área de trabalho do teams instalado. O suplemento de reunião não será instalado quando você usar somente o cliente Web Teams.
- Verifique se o usuário tem o Outlook 2013 ou posterior instalado.
- Certifique-se de que o usuário tenha permissão para executar o regsvr32. exe.
- Certifique-se de que todas as atualizações disponíveis para o cliente da área de trabalho do Outlook foram aplicadas.
- Siga estas etapas:
  - Reinicie o cliente de área de trabalho do Teams.
  - Saia e entre novamente no cliente de área de trabalho do Teams.
  - Reinicie o cliente para área de trabalho do Outlook. (Verifique se o Outlook não está em execução no modo de administração.)

Se você ainda não vir o suplemento, certifique-se de que ele não esteja desabilitado no Outlook.

- No Outlook, escolha **arquivo** e, em seguida, **Opções**.
- Selecione a **guia suplementos da** caixa de diálogo **Opções do Outlook** .
- Confirme se o **suplemento de reunião do Microsoft Teams para Microsoft Office** está listado na lista de **suplementos do aplicativo ativo**
- Se o suplemento de reunião do teams estiver listado na lista de **suplementos de aplicativo desabilitada** , selecione suplementos de **com** em **gerenciar** e, em seguida, selecione **ir...**
- Defina a caixa de seleção ao lado de **suplemento de reunião do Microsoft Teams para Microsoft Office**.
- Escolha **OK** em todas as caixas de diálogo e reinicie o Outlook.

Para obter orientação geral sobre como gerenciar suplementos, consulte [Exibir, gerenciar e instalar suplementos em programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Se o suplemento ainda não for exibido, use as etapas a seguir para verificar as configurações do registro.

> [!NOTE]
> A edição incorreta do registro pode danificar seriamente seu sistema. Antes de fazer alterações no registro, você deve fazer backup de todos os dados importantes do computador.
- Inicie o RegEdit. exe
- Navegue até HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins
- Verifique se o TeamsAddin. FastConnect existe.
- Em TeamsAddin. FastConnect, verifique se existe LoadBehavior e se está definido como 3.
  - Se LoadBehavior tiver um valor diferente de 3, altere-o para 3 e reinicie o Outlook.

### <a name="delegate-scheduling-does-not-work"></a>O agendamento de representante não funciona

Se o seu administrador configurou o Microsoft Exchange para [controlar o acesso ao Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), um representante não poderá agendar uma reunião do Teams em nome do chefe. A solução para esta configuração está em desenvolvimento e será lançada no futuro. 
