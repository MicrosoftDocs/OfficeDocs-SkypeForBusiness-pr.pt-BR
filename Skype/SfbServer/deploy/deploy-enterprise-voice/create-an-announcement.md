---
title: Criar ou excluir um comunicado no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Crie ou exclua comunicados para o aplicativo De comunicado Skype for Business Server Enterprise Voice. Isso afeta como as chamadas para números não atribuídos são manipuladas.
ms.openlocfilehash: 3a5fdbcb5f9c4e72790f35f73cef791868634ce9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765919"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Criar ou excluir um comunicado no Skype for Business Server

Crie ou exclua comunicados para o aplicativo De comunicado Skype for Business Server Enterprise Voice. Isso afeta como as chamadas para números não atribuídos são manipuladas.

Ao configurar comunicados, na verdade você está configurando como deseja manipular as chamadas para números não atribuídos. É possível reproduzir um prompt, que pode ser um arquivo de áudio ou um arquivo TTS (conversão de texto em fala) ou simplesmente transferir a chamada para um destino especificado sem reproduzir um prompt.

Você precisa criar anúncios antes de definir a tabela de números não atribuídos. Você precisa executar esta etapa para todos os anúncios que usam um prompt de áudio, de TTS ou nenhum prompt.

Este tópico descreve como importar e criar comunicados. Para obter detalhes sobre como atribuir comunicados na tabela de números não atribuídos, consulte [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Criar um novo comunicado para números não atribuídos

Para criar um novo comunicado, é necessário executar as seguintes etapas:

1. Para prompts de áudio, grave o arquivo de áudio usando seu aplicativo de gravação de áudio favorito.

2. Para prompts de áudio, execute o cmdlet **Import-CsAnnouncementFile** para importar o conteúdo do arquivo de áudio para o Repositório de Arquivos.

3. Execute o cmdlet **New-CsAnnouncement** para criar e nomear o comunicado. Execute esta etapa para criar comunicados com um prompt de áudio, um prompt TTS (text-to-speech), ou sem prompt.


    > [!TIP]
    > Pode ser desejável criar um comunicado sem prompt (por exemplo, se você deseja transferir chamadas para um destino específico sem reproduzir uma mensagem).

4. Atribua o novo comunicado a um intervalo numérico na tabela de números não atribuídos.

### <a name="to-create-a-new-announcement"></a>Para criar um novo comunicado

1. Para prompts de áudio, crie o arquivo de áudio.

2. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários** conforme descrito em Permissões de Instalação do Representante .

3. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

4. Para prompts de áudio, execute:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Execute .

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Para transferir chamadas para a caixa postal, digite o SIPAddress no formato sip:nomedousuário@nomedodomínio;opaque=app:voicemail (por exemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir chamadas para um número de telefone, digite o SIPAddress no formato sip:número@nomedodomínio;user=phone (por exemplo, sip:+ 14255550121@contoso.com;user=phone).

    Por exemplo, para especificar um prompt de áudio:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Por exemplo, para especificar um prompt TTS:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Para obter mais detalhes sobre esses cmdlets e para ver uma lista dos códigos de idioma a ser usado no parâmetro **TextToSpeechPrompt,** consulte [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Excluir um comunicado para números não atribuídos

### <a name="to-delete-an-announcement"></a>Para excluir um anúncio

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários** conforme descrito em Permissões de Instalação do Representante .

2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

3. Lista todos os anúncios em sua organização. Na linha de comando, execute:

   ```powershell
   Get-CsAnnouncement
   ```

4. Na lista resultante, localize o anúncio que deseja excluir e copie o GUID. Na linha de comando, execute:

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Por exemplo:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Para obter detalhes sobre mais opções, consulte [Get-CsAnnouncement e](/powershell/module/skype/get-csannouncement?view=skype-ps) [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Confira também

[Criar ou excluir um comunicado no Skype for Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)