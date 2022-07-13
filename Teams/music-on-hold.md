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
ms.openlocfilehash: 9d8fa247ffdc982c5d41777c68f6b620a92644e3
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773750"
---
# <a name="music-on-hold"></a>Música em Espera

Quando um usuário do Microsoft Teams coloca uma chamada de entrada em espera, o chamador pode ouvir a música selecionada.

A música que é tocada é a música padrão fornecida pela Microsoft ou a música personalizada que você carrega e configura. Como administrador de locatários, você configura se a Música em Espera está disponível criando uma política de chamada do Teams e atribuindo a política ao usuário do Teams.

A música padrão fornecida nos cenários de chamada do Microsoft Teams é livre de royalties a pagar pela sua organização.

Observe que os chamadores também podem ouvir Música em Espera em outros cenários; por exemplo, quando eles chamam uma Fila de Chamadas na Nuvem ou quando sua chamada é estacionada por um usuário do Microsoft Teams. Esses cenários não são cobertos nem controlados pelos recursos mencionados neste artigo.

## <a name="configure-music-on-hold"></a>Configurar Música em Espera

Para configurar Música em Espera:

1. No painel de navegação esquerdo do Centro de administração do Teams, vá para **Políticas de Chamada > Voz**.

2. Na guia **Gerenciar políticas** , selecione uma das políticas existentes ou crie uma nova.

3. No campo **Música em espera para chamadores PSTN****, selecione** Habilitado no menu suspenso.

Você também pode configurar Música em Espera usando o módulo do PowerShell do Teams. No TeamsCallingPolicy, altere o parâmetro MusicOnHoldEnabledType para Habilitado e conceda essa instância de política a um ou mais usuários.

Se um usuário do Teams tiver uma política de chamada do Teams com Música em Espera definida como Desabilitada, nenhuma música será tocada quando o usuário do Teams colocar a chamada em espera.

## <a name="configure-custom-music"></a>Configurar música personalizada

Além de reproduzir música padrão para chamadores, você pode carregar um arquivo de áudio personalizado com música ou outro conteúdo de áudio e configurar esse arquivo de áudio para ser reproduzido para o chamador.
Por exemplo, um departamento ou organização pode querer reproduzir um anúncio personalizado ou música personalizada quando chamadores PSTN externos são colocados em espera.

A configuração é feita usando políticas de retenção de chamada.

> [!NOTE]
> Você é responsável por limpar e proteger independentemente todos os direitos e permissões necessários para usar qualquer arquivo de música ou áudio com seu serviço do Microsoft Teams. Isso pode incluir propriedade intelectual e outros direitos em qualquer música, efeitos sonoros, áudio, marcas, nomes e outros conteúdos no arquivo de áudio de todos os titulares de direitos relevantes. Os titulares podem incluir artistas, atores, artistas, músicos, compositores, compositores, gravadoras, editores de música, sindicatos, grêmios, sociedades de direitos, organizações de gestão coletiva e quaisquer outras partes que possuirem, controlar ou licenciar os direitos autorais de música, efeitos sonoros, áudio e outros direitos de propriedade intelectual.

### <a name="use-the-teams-admin-center"></a>Usar o centro de administração do Teams
Você pode usar o Centro de administração do Teams para configurar músicas personalizadas em espera para seus usuários criando ou editando políticas de retenção de chamadas.

Para configurar uma nova política de retenção de chamada:

1. No centro de administração do Teams, vá para políticas **de** > **retenção de Chamada de Voz**.

2. Selecione a **guia** Adicionar.

3. Dê um nome e uma descrição à política.

4. Selecione **Carregar arquivo** para carregar o arquivo de áudio de música personalizado.

5. Selecione **Aplicar**.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>Atribuir uma política de retenção de chamada personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>Usar o PowerShell
Para configurar música em espera personalizada, use os cmdlets do PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile no módulo do PowerShell do Teams 3.0.0 ou posterior.

Para formatos de áudio com suporte e tamanho máximo de arquivo, consulte [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Verifique se o usuário do Teams tem Música em espera para chamadores PSTN definido como Habilitado na política de chamada do Teams. 

2. Carregue o arquivo de áudio personalizado.

3. Crie uma política de Retenção de Chamada do Teams que referencie o arquivo de áudio personalizado e atribua-o ao usuário do Teams.

### <a name="upload-the-custom-audio-file"></a>Carregar o arquivo de áudio personalizado

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

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fazer referência ao arquivo de áudio em uma Política de Retenção de Chamada do Teams

Depois de carregar o arquivo de áudio, você precisa fazer referência ao arquivo em uma Política de Retenção de Chamada do Teams usando a ID do arquivo ao criar ou definir uma Política de Retenção de Chamada do Teams. Por exemplo:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Depois de criar a nova Política de Retenção de Chamadas do Teams, você pode concedi-la aos usuários usando Grant-CsTeamsCallHoldPolicy da seguinte maneira:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Para obter informações sobre os arquivos de áudio carregados, use Get-CsOnlineAudioFile cmdlet.

Para remover um arquivo de áudio carregado, use o Remove-CsOnlineAudioFile cmdlet. Antes de remover um arquivo de áudio, verifique se você não está usando esse arquivo de áudio em um TeamsCallHoldPolicy.

Para exportar um arquivo de áudio carregado, use Export-CsOnlineAudioFile cmdlet.

## <a name="feature-availability"></a>Disponibilidade de recursos

A tabela a seguir indica quais recursos os clientes e dispositivos dão suporte a Música em Espera e Música Personalizada em Espera. A Microsoft continua adicionando suporte a recursos, portanto, verifique com frequência se há disponibilidade adicional.

| Recurso | Desktop <br> Windows/Mac OS | Navegador | Mobile <br> iOS | Mobile <br> Android | Telefone do Teams |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Espera na chamada PSTN 1:1 | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |
| Espera na chamada do Teams 1:1 | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |
| Espera na Transferência Consultativa na chamada PSTN 1:1 |-Música em Espera<br>-Custom Music on Hold || -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |
| Espera na Transferência Consultiva na chamada do Teams 1:1 |-Música em Espera<br>-Custom Music on Hold || -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold | -Música em Espera<br>-Custom Music on Hold |

## <a name="restrictions"></a>Restrições

- A música em espera só está disponível em instâncias de nuvem comerciais e GCC.

- A música em espera só está disponível quando o usuário está no modo TeamsOnly.

- Se o usuário chamado do Teams estiver habilitado para Location-Based roteamento, a música em espera não poderá ser tocada para o chamador.

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
