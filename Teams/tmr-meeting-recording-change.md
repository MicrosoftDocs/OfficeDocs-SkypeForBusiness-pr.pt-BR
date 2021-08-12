---
title: Use o OneDrive for Business e SharePoint o Online para gravações de reuniões
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como alternar do armazenamento de gravação de reunião do Stream para o OneDrive for Business e SharePoint no Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bbde1b4d5425b0bbcf904528f0ddb232f27a2ba4b15fb0755639ef01b1f5f09f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312439"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Use o OneDrive for Business e o SharePoint Online ou o Stream para gravações de reuniões

> [!Note]
> A alteração do uso do Microsoft Stream para o OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reuniões será uma abordagem em fases.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 de outubro de 2020<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Você habilita a política de Reuniões do Microsoft Teams para que as gravações de reuniões sejam salvas no OneDrive for Business e no SharePoint Online em vez do Microsoft Stream (Clássico)|
|A implantação começa em 7 de janeiro de 2021<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas as novas gravações de reuniões do Teams serão salvas no OneDrive for Business e no SharePoint Online, a menos que você atrase essa alteração modificando as políticas de Reuniões do Microsoft Teams da sua organização e definindo-as explicitamente para o **Stream**. Ver o relatório de política como Stream não é suficiente. Você precisa definir explicitamente o valor da política para **Stream**.|
|A implantação começa em 11 de janeiro de 2021<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC**<br> Embora os clientes GCC possam recusar a partir de 5 de outubro, você não pode aceitar. Este recurso será implantado para todos os clientes GCC a partir de 11 de janeiro de 2021, a menos que você tenha recusado.<br>  <br>A partir de 11 de janeiro de 2021, todas as novas gravações de reuniões do Teams para clientes GCC serão salvas no OneDrive for Business e no SharePoint Online, a menos que você atrase essa alteração modificando as políticas de reuniões do Teams da sua organização e definindo-as explicitamente para o **Stream**. <br><br>Se você recusou mas está pronto para ativar este recurso, pode fazê-lo configurando explicitamente a Política de Reunião do Teams para **OneDrive for Business**. |
|Em implantação a partir de 1 de março de 2021<br> *(Completo)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC alto e DoD**<br> Agora, os clientes podem habilitar gravações de reunião na nuvem em seus Microsoft Teams pela primeira vez. Essas gravações serão armazenadas e reproduzidas no OneDrive e no SharePoint Online por padrão. |
|Em implantação a partir de 7 de julho de 2021<br> *(Completo)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos os clientes (Enterprise, Education e GCC)**<br> Para uma reunião do Microsoft Teams que foi gravada no OneDrive e no SharePoint Online e também transcrita ao vivo durante a reunião, agora você pode pesquisar na Pesquisa da Microsoft para encontrar o arquivo de gravação da reunião com base na transcrição. |
|Em implantação incremental a partir de 16 de agosto de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos os clientes (Enterprise, Education e GCC)**<br>Nenhuma nova gravação de reunião pode ser salva no Microsoft Stream (Clássico); todos os clientes terão gravações de reuniões salvas automaticamente no OneDrive for Business e no SharePoint Online, mesmo que tenham alterado as políticas de reunião de suas equipes para o Stream.<br><br> Recomendamos que os clientes, para controlar melhor a alteração na sua organização, aceitem quando estiverem confortáveis com a alteração em vez de esperar que ela aconteça. |

O Microsoft Teams tem um novo método para salvar gravações de reunião. Como a primeira fase de uma transição do Microsoft Stream clássico para o [novo Stream](/stream/streamnew/new-stream), este método armazena gravações no Microsoft OneDrive for Business e SharePoint Online no Microsoft 365 e oferece muitos benefícios.

O Stream (clássico) como plataforma não será descontinuado em um futuro próximo. Os vídeos atualmente ao vivo no Stream (clássico) ficarão lá até que uma ferramenta de migração futura esteja disponível para movê-los para o OneDrive e o SharePoint Online. Consulte [Migração do Stream Clássico](/stream/streamnew/classic-migration) para obter mais informações sobre nossos planos futuros.

> [!NOTE]
> Se a gravação de uma reunião do Microsoft Teams não for carregada com êxito para o OneDrive/SharePoint Online, a gravação será temporariamente salva no Serviços de Mídia do Microsoft Azure (AMS). Depois de armazenada no AMS, nenhuma nova tentativa será feita para carregar automaticamente a gravação no OneDrive/SharePoint Online ou Stream.

As gravações de reuniões armazenadas no AMS ficam disponíveis por 21 dias antes de serem excluídas automaticamente. Os usuários podem baixar o vídeo do AMS se precisarem manter uma cópia.

Os benefícios de usar o OneDrive for Business e o SharePoint Online para armazenar gravações incluem:

- Políticas de retenção para gravação de reunião do Teams (TMR) (rótulos de retenção automática S+C E5)
- Desfrute do OneDrive for Business e da governança de informações do SharePoint Online
- Fácil de definir permissões e compartilhamento
- Compartilhe gravações com convidados (usuários externos) com somente compartilhamento explícito.
- Solicite o fluxo de acesso
- Fornece links compartilhados do OneDrive for Business e do SharePoint Online
- As gravações de reunião ficam disponíveis mais rapidamente
- Transcrição da base de pesquisa gravada na sua reunião
- Suporte ao locatário do **Fique no Local** 
- Suporte Multi-Geo - As gravações são armazenadas em uma região específica para esse usuário
- Suporte ao Bring Your Own Key (BYOK)

Veja a lista completa de [recursos disponíveis hoje e o que esperar ao longo do tempo](/stream/streamnew/features-new-version-stream).

Veja "Novidades nas gravações de reuniões do Microsoft Teams" para obter mais informações.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configure a opção de gravação de reunião para OneDrive for Business e SharePoint Online

A opção de gravação de reunião é uma configuração no nível de política do Teams. O exemplo a seguir mostra como definir a política Global. Certifique-se de que configurou a opção de gravação de reunião para a política ou políticas que atribuiu aos seus usuários.

> [!Note]
> As alterações na política de reunião do Teams levam algum tempo para serem propagadas. Verifique novamente após algumas horas após defini-la, saia e entre novamente no aplicativo Área de Trabalho do Teams ou simplesmente reinicie o computador.

1. Instalar o PowerShell do Teams.

   > [!NOTE]
   > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online. Confira [Gerenciar o Skype for Business Online com o PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Abra o PowerShell como um administrador.

3. Instale o [módulo do PowerShell do Teams](./teams-powershell-install.md).

4. Importe o módulo do Microsoft Teams e entre como um administrador do Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Use [Set CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para definir uma Política de Reunião do Microsoft Teams para fazer a transição do armazenamento do Stream para o do OneDrive for Business e SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se alguns de seus usuários tiverem designado uma política por organizador ou por usuário, você deve definir esta configuração nesta política se quiser que eles também armazenem as gravações da reunião no OneDrive for Business e no SharePoint Online. Para mais informações, confira [Gerenciar políticas de reunião no Microsoft Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Saiba mais

Para saber mais sobre a gravação de reunião na nuvem do Teams, consulte [Gravação de reuniões na nuvem do Microsoft Teams](cloud-recording.md). Nesse artigo, você pode aprender mais sobre configuração de gravação, gerenciamento, governança, permissões e armazenamento.
