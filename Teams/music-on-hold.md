---
title: Música em Espera
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
ms.custom: ''
description: Saiba como gerenciar o recurso Música em Espera no Sistema de Telefonia.
ms.openlocfilehash: 4899ffd2a3b6bfda80164ca2df4a5460a2b005e2
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624239"
---
# <a name="music-on-hold"></a>Música em Espera

Quando um Microsoft Teams usuário coloca uma chamada de entrada em espera, o chamador pode ouvir a música selecionada.

A música que é tocada é a música padrão fornecida pela Microsoft ou a música personalizada que você carrega e configura. Como o administrador de locatários, você configura se a música em espera está disponível criando uma política de chamada Teams e atribuindo a política ao Teams usuário.

A música padrão fornecida em cenários Microsoft Teams chamada é livre de royalties a pagar pela sua organização.

Observe que os chamadores também podem ouvir Música em Espera em outros cenários; por exemplo, quando eles chamam uma Fila de Chamadas na Nuvem ou quando sua chamada é estacionada por um Microsoft Teams usuário. Esses cenários não são cobertos nem controlados pelos recursos mencionados neste artigo.

## <a name="configure-music-on-hold"></a>Configurar Música em Espera

Para configurar Música em Espera:

1.  No painel de navegação esquerdo do Teams de administração, vá para **Políticas de Chamada > Voz**.

2.  Na guia **Gerenciar políticas** , selecione uma das políticas existentes ou crie uma nova.

3.  No campo **Música em espera para chamadores PSTN****, selecione** Habilitado no menu suspenso.

Você também pode configurar Música em Espera usando o módulo Teams PowerShell. No TeamsCallingPolicy, altere o parâmetro MusicOnHoldEnabledType para Habilitado e conceda essa instância de política a um ou mais usuários.

Se um Teams tiver uma política de chamada Teams com Música em Espera definida como Desabilitada, nenhuma música será tocada quando o usuário Teams colocar a chamada em espera.

## <a name="configure-custom-music"></a>Configurar música personalizada

Além de reproduzir música padrão para chamadores, você pode carregar um arquivo de áudio personalizado com música ou outro conteúdo de áudio e configurar esse arquivo de áudio para ser reproduzido para o chamador.
Por exemplo, um departamento ou organização pode querer reproduzir um anúncio personalizado ou música personalizada quando chamadores PSTN externos são colocados em espera.  

> [!NOTE]
> Você é responsável por limpar e proteger independentemente todos os direitos e permissões necessários para usar qualquer arquivo de música ou áudio com seu Microsoft Teams serviço. Isso pode incluir propriedade intelectual e outros direitos em qualquer música, efeitos sonoros, áudio, marcas, nomes e outros conteúdos no arquivo de áudio de todos os titulares de direitos relevantes. Os titulares podem incluir artistas, atores, artistas, músicos, compositores, compositores, gravadoras, editores de música, sindicatos, grêmios, sociedades de direitos, organizações de gestão coletiva e quaisquer outras partes que possuirem, controlar ou licenciar os direitos autorais de música, efeitos sonoros, áudio e outros direitos de propriedade intelectual.

Para configurar música em espera personalizada, use os cmdlets do PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile no módulo 3.0.0 ou posterior do PowerShell do Teams.

Para formatos de áudio com suporte e tamanho máximo de arquivo, consulte [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)


1. Verifique se o Teams tem Música em espera para chamadores PSTN definido como Habilitado na política Teams chamada. 

2. Upload arquivo de áudio personalizado.

3. Crie uma Teams de Espera de Chamada referenciando o arquivo de áudio personalizado e atribua-o ao Teams usuário.

### <a name="upload-the-custom-audio-file"></a>Upload o arquivo de áudio personalizado

A configuração de Música em Espera personalizada começa com o carregamento do arquivo de áudio. Use o cmdlet [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) do PowerShell para essa finalidade.

Um exemplo de carregamento de um arquivo de áudio MP3 usando Windows PowerShell 5.1 é mostrado abaixo. Para obter outros exemplos, [consulte Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fazer referência ao arquivo de áudio em uma Teams de Espera de Chamada

Depois de carregar o arquivo de áudio, você precisa fazer referência ao arquivo em uma Política de Retenção de Chamada do Teams usando a ID do arquivo ao criar ou definir uma Política de Retenção de Chamada Teams. Por exemplo:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Depois de criar a nova política de Teams chamada, você poderá concedi-la aos usuários usando Grant-CsTeamsCallHoldPolicy a seguir:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Para obter informações sobre os arquivos de áudio carregados, use Get-CsOnlineAudioFile cmdlet.

Para remover um arquivo de áudio carregado, use o Remove-CsOnlineAudioFile cmdlet. Antes de remover um arquivo de áudio, verifique se você não está usando esse arquivo de áudio em um TeamsCallHoldPolicy.

Para exportar um arquivo de áudio carregado, use Export-CsOnlineAudioFile cmdlet.

## <a name="feature-availability"></a>Disponibilidade de recursos

A tabela a seguir indica quais recursos os clientes e dispositivos dão suporte a Música em Espera e Música Personalizada em Espera. A Microsoft continua adicionando suporte a recursos, portanto, verifique com frequência se há disponibilidade adicional.


| Recurso | Desktop <br> Windows/Mac OS | Navegador | Mobile <br> iOS | Mobile <br> Android | Teams Telefone |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Espera na chamada PSTN 1:1 | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |
| Espera 1:1 Teams chamada | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |
| Espera na Transferência Consultativa na chamada PSTN 1:1 |-Música em Espera<br>-Custom Music on Hold || -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |
| Manter a transferência consultativa em uma chamada de Teams 1:1 |-Música em Espera<br>-Custom Music on Hold || -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |

## <a name="restrictions"></a>Restrições

- A música em espera só está disponível em instâncias comerciais e GCC nuvem.

- A música em espera só está disponível quando o usuário está no modo TeamsOnly.

- Se o usuário Teams chamado estiver habilitado para roteamento Location-Based, a música em espera não poderá ser tocada para o chamador.

- A Música Personalizada em Espera não está disponível para usuários configurados para Aparência de Linha Compartilhada (delegação) e quando o Estacionamento de Chamada é usado. A música padrão em espera será tocada.

- Em alguns cenários, uma chamada de bypass de mídia de Roteamento Direto será convertida em bypass de não mídia para reproduzir Música em Espera e a chamada permanecerá como bypass de não mídia até que a chamada seja encerrada.

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

