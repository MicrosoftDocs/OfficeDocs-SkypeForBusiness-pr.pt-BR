---
title: Música em espera
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 845e85fbf7fb4fa9f5ee70769c6a66f49cd8bb4e
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432774"
---
# <a name="music-on-hold"></a>Música em espera

Quando um Microsoft Teams coloca uma chamada de entrada da PSTN (Rede Telefônica Pública Comutado) em espera, o chamador PSTN pode ouvir música selecionada.

A música que é tocada é a música padrão fornecida pela Microsoft ou a música personalizada que você carrega e configura. Como administrador de locatários, você configura se a Música em Espera está disponível usando a Política de Chamada Teams e atribuindo a política ao usuário Teams usuário. 

Observe que os chamadores PSTN também podem ouvir Música em Espera em outros cenários; por exemplo, quando eles chamam em uma Fila de Chamada na Nuvem ou quando sua chamada é estacionada por um Microsoft Teams usuário. Esses cenários não são cobertos ou controlados pelos recursos mencionados neste artigo. 

## <a name="configure-music-on-hold"></a>Configurar Música em Espera

Para configurar Música em Espera:

1.  Na navegação à esquerda do centro de administração Teams, acesse **Voice > Calling policies**.

2.  Na guia **Gerenciar políticas,** selecione uma das políticas existentes ou crie uma nova.

3.  No campo Música em espera para **chamadores PSTN,** selecione **Habilitado** no menu suspenso.

Você também pode configurar Música em Espera usando o módulo Teams PowerShell. No TeamsCallingPolicy, altere o parâmetro MusicOnHoldEnabledType para Habilitado e conceda essa instância de política a um ou mais usuários.

Se um usuário Teams tiver uma política de chamada Teams música em espera definida como Desabilitada, nenhuma música será tocada quando o usuário Teams colocar a chamada em espera.

## <a name="configure-custom-music"></a>Configurar música personalizada

> [!NOTE]
> Esse recurso está disponível como uma versão de Visualização Pública.

Além de tocar música padrão para chamadores PSTN, você pode carregar um arquivo de áudio personalizado com música ou outro conteúdo de áudio e configurar esse arquivo de áudio a ser tocado para o chamador PSTN.
Por exemplo, um departamento ou organização pode querer reproduzir um anúncio personalizado ou música personalizada quando os chamadores PSTN externos são colocados em espera.  

> [!NOTE]
> Você é responsável por limpar e proteger independentemente todos os direitos e permissões necessários para usar qualquer arquivo de música ou áudio com seu Microsoft Teams serviço. Isso pode incluir propriedade intelectual e outros direitos em qualquer música, efeitos sonoros, áudio, marcas, nomes e outros conteúdos no arquivo de áudio de todos os titulares de direitos relevantes. Os proprietários podem incluir artistas, atores, atores, compositores, compositores, rótulos de gravação, editores de música, sindicatos, guildas, sociedades de direitos, organizações de gerenciamento coletivo e quaisquer outras partes que têm, controlam ou licenciam os direitos autorais de música, efeitos sonoros, áudio e outros direitos de propriedade intelectual.

Para configurar música em espera personalizada, use os cmdlets Do PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove-CsOnlineAudioFile Teams no módulo 2.5.0 ou posterior do PowerShell.


1. Verifique se o usuário Teams música em espera para chamadores PSTN definido como Habilitado na Política de Teams Chamada. 

2. Upload arquivo de áudio personalizado.

3. Crie uma Teams de chamada de chamada fazendo referência ao arquivo de áudio personalizado e atribua-o ao usuário Teams usuário.

### <a name="upload-the-custom-audio-file"></a>Upload o arquivo de áudio personalizado

A configuração do Music On Hold personalizado começa com o carregamento do arquivo de áudio. Você usa o cmdlet do PowerShell Import-CsOnlineAudioFile para essa finalidade. Um exemplo de carregamento de um arquivo de áudio MP3 usando a interface do PowerShell é mostrado abaixo:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fazer referência ao arquivo de áudio em uma política de Teams de chamada

Depois de carregar o arquivo de áudio, você precisará fazer referência ao arquivo em uma Política de Espera de Chamada Teams usando a ID do arquivo ao criar ou definir uma Política de Espera de Chamada Teams de chamada. Por exemplo:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Depois de criar a nova Política de Teams de Chamada, você poderá concedi-la aos usuários usando Grant-CsTeamsCallHoldPolicy a seguir:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Para obter informações sobre seus arquivos de áudio carregados, use Get-CsOnlineAudioFile cmdlet.

Para remover um arquivo de áudio carregado, use o Remove-CsOnlineAudioFile cmdlet. Antes de remover um arquivo de áudio, verifique se você não está usando esse arquivo de áudio em um TeamsCallHoldPolicy.

## <a name="restrictions"></a>Restrições

- Música em espera só está disponível na nuvem comercial.

- A música em espera só estará disponível quando o usuário estiver Teams modo Somente.

- Música em espera não está disponível quando o usuário Teams faz transferência consultiva.

- Se o usuário Teams chamado estiver habilitado para roteamento Location-Based, a música em espera não poderá ser tocada para o chamador.

-   A música em espera só estará disponível quando o usuário Teams chamado estiver usando uma das seguintes versões do Teams cliente:
    -   Microsoft Teams para Windows
    -   Microsoft Teams para Mac
    -   Microsoft Teams na Web
    -   Microsoft Teams para iOS
    - Microsoft Teams para Android
<br>
- Não é possível exportar o arquivo de áudio depois que ele tiver sido carregado; você só pode removê-lo.

- Música personalizada em espera não está disponível para usuários configurados para Aparência de Linha Compartilhada (delegação) e quando Estacionamento de Chamada é usado. A música padrão em espera será tocada.

- Em alguns cenários, uma chamada de bypass de mídia de Roteamento Direto será convertida em bypass de não mídia para reprodução de Música em Espera e a chamada permanecerá como bypass de não mídia até que a chamada seja encerrada.



## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)




