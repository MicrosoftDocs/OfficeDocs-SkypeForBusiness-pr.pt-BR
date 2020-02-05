---
title: Criar ou excluir um comunicado no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Criar ou excluir comunicados para o aplicativo de anúncio no Skype for Business Server Enterprise Voice. Isso afeta o modo como nas chamadas para números não atribuídos são administradas.
ms.openlocfilehash: 7cde8c268c66d19e6806a4b6c3e585a7271ef2ff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767954"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Criar ou excluir um comunicado no Skype for Business Server

Criar ou excluir comunicados para o aplicativo de anúncio no Skype for Business Server Enterprise Voice. Isso afeta como o sistema lida com as chamadas para números não atribuídos.

Ao configurar comunicados, na verdade você está configurando como deseja manipular as chamadas para números não atribuídos. É possível reproduzir um prompt, que pode ser um arquivo de áudio ou um arquivo TTS (conversão de texto em fala) ou simplesmente transferir a chamada para um destino especificado sem reproduzir um prompt.

Você precisa criar anúncios antes de definir a tabela de números não atribuídos. Você precisa executar esta etapa para todos os anúncios que usam um prompt de áudio, de TTS ou nenhum prompt.

Este tópico descreve como importar e criar comunicados. Para obter detalhes sobre como atribuir comunicados na tabela de números não atribuídos, consulte [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).

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

2. Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.

3. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

4. Para prompts de áudio, execute:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Execute:

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

   Para obter mais detalhes sobre esses cmdlets e ver uma lista dos códigos de idioma a serem usados no parâmetro **TextToSpeechPrompt** , consulte [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Excluir um comunicado para números não atribuídos

### <a name="to-delete-an-announcement"></a>Para excluir um anúncio

1. Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

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
    > Para obter detalhes sobre mais opções, consulte [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) e [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Confira também

[Criar ou excluir um comunicado no Skype for Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

