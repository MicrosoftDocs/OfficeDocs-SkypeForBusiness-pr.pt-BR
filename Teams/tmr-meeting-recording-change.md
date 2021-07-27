---
title: Use OneDrive for Business e SharePoint Online para gravações de reunião
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como alternar do Stream para o OneDrive for Business e SharePoint armazenamento de gravação de reuniões online Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486131"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Use OneDrive for Business e SharePoint Online ou Stream para gravações de reunião

> [!Note]
> A alteração de usar o Microsoft Stream para OneDrive for Business e Microsoft Office SharePoint Online para gravações de reunião será uma abordagem em fases.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 de outubro de 2020<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Você permite que a Teams de reunião tenha gravações de reunião salvas no OneDrive for Business e SharePoint Online em vez do Microsoft Stream (Clássico)|
|A implantação começa em 7 de janeiro de 2021<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas as novas Teams de reunião serão salvas no OneDrive for Business e no SharePoint Online, a menos que você atrase essa alteração modificando as políticas de reunião do Teams da sua organização e definindo-as explicitamente como **Stream**. Ver o relatório de política como Stream não é suficiente. Você precisa definir explicitamente o valor da política para **Stream**.|
|A implantação começa em 11 de janeiro de 2021<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC**<br> Embora os clientes GCC possam recusar a partir de 5 de outubro, você não pode aceitar. Este recurso será implantado para todos os clientes GCC a partir de 11 de janeiro de 2021, a menos que você tenha recusado.<br>  <br>A partir de 11 de janeiro de 2021, todas as novas gravações de reunião do Teams para clientes do GCC serão salvas no OneDrive for Business e no SharePoint Online, a menos que você atrase essa alteração modificando as políticas de reunião do Teams da sua organização e definindo-as explicitamente como **Stream**. <br><br>Se você recusou mas está pronto para ativar este recurso, pode fazê-lo configurando explicitamente a Política de Reunião do Teams para **OneDrive for Business**. |
|A implantação começa em 1º de março de 2021 <br> *(Concluído)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC alto e DoD**<br> Agora, os clientes podem habilitar gravações de reunião na nuvem em seus Microsoft Teams pela primeira vez. Essas gravações serão armazenadas e tocadas em OneDrive e SharePoint Online por padrão. |
|Implantando a partir de 7 de julho de 2021<br> *(Concluído)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos os clientes (Enterprise, Education e GCC)**<br> Para uma reunião Teams que foi gravada no OneDrive e no SharePoint Online e também foi transcrita ao vivo durante a reunião, agora você pode pesquisar no Pesquisa da Microsoft para encontrar o arquivo de gravação da reunião com base na transcrição. |
|Implantando incrementalmente a partir de 16 de agosto de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos os clientes (Enterprise, Education e GCC)**<br>Nenhuma nova gravação de reunião pode ser salva no Microsoft Stream (Clássico); todos os clientes terão automaticamente gravações de reunião salvas no OneDrive for Business e SharePoint Online, mesmo que tenham alterado suas políticas de reunião Teams para Stream.<br><br> Recomendamos que os clientes, para controlar melhor a alteração na sua organização, aceitem quando estiverem confortáveis com a alteração em vez de esperar que ela aconteça. |

O Microsoft Teams tem um novo método para salvar gravações de reunião. Como a primeira fase de uma transição do Microsoft Stream clássico para o novo [Stream](/stream/streamnew/new-stream), esse método armazena gravações no Microsoft OneDrive para Empresas e SharePoint Online no Microsoft 365 e oferece muitos benefícios.

Stream (clássico) como uma plataforma não será preterido em um futuro próximo. Os vídeos que atualmente vivem no Stream (clássico) permanecerão lá até que uma ferramenta de migração futura fique disponível para movê-los para OneDrive e SharePoint Online. Verifique [a migração clássica do Stream](/stream/streamnew/classic-migration) para obter mais informações sobre nossos planos futuros.

> [!NOTE]
> Se uma gravação Teams de reunião falhar ao carregar com êxito no OneDrive/SharePoint Online, a gravação será salva temporariamente no Serviços de Mídia do Azure (AMS). Depois de armazenado no AMS, nenhuma tentativa de nova tentativa é feita para carregar automaticamente a gravação para OneDrive/SharePoint Online ou Stream.

As gravações de reunião armazenadas no AMS estão disponíveis por 21 dias antes de serem excluídas automaticamente. Os usuários podem baixar o vídeo do AMS se precisarem manter uma cópia.

Os benefícios de usar OneDrive for Business e SharePoint Online para armazenar gravações incluem:

- Políticas de retenção para gravação de reunião do Teams (TMR) (rótulos de retenção automática S+C E5)
- Beneficiar-se OneDrive for Business e SharePoint de informações online
- Fácil de definir permissões e compartilhamento
- Compartilhe gravações com convidados (usuários externos) com somente compartilhamento explícito.
- Solicite o fluxo de acesso
- Fornecer OneDrive for Business e SharePoint online compartilhados
- As gravações de reunião ficam disponíveis mais rapidamente
- Transcrição de base de pesquisa gravada em sua reunião
- Suporte ao locatário do **Fique no Local** 
- Suporte Multi-Geo - As gravações são armazenadas em uma região específica para esse usuário
- Suporte ao Bring Your Own Key (BYOK)

Consulte a lista completa de [recursos disponíveis hoje e o que esperar ao longo do tempo.](/stream/streamnew/features-new-version-stream)

Assista a "What's New for Microsoft Teams Meeting Recordings" para obter mais informações.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configurar a opção de gravação de reunião para OneDrive for Business e SharePoint Online

A opção de gravação de reunião é uma configuração no nível de política do Teams. O exemplo a seguir mostra como definir a política Global. Certifique-se de que configurou a opção de gravação de reunião para a política ou políticas que atribuiu aos seus usuários.

> [!Note]
> Teams da política de reunião levam um tempo para se propagar. Faça check-back após algumas horas de defini-lo, em seguida, saia e entre no aplicativo Teams desktop novamente ou simplesmente reinicie o computador.

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

5. Use [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para definir uma Política de Reunião Teams para fazer a transição do armazenamento stream para OneDrive for Business e SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se alguns de seus usuários tiver atribuído uma política por organizador ou por usuário, você deverá definir essa configuração nesta política se quiser que eles também armazenem as gravações de reunião no OneDrive for Business e no SharePoint Online. Para mais informações, confira [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Saiba mais

Para saber mais sobre Teams de reunião na nuvem, [consulte Teams gravação de reunião na nuvem.](cloud-recording.md) Nesse artigo, você pode saber mais sobre a configuração de gravação, gerenciamento, governança, permissões e armazenamento.
