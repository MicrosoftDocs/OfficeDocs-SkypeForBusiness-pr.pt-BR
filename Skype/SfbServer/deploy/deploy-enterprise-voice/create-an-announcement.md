---
title: Criar ou excluir um anúncio no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Criar ou excluir comunicados para o aplicativo de anúncio no Skype para Business Server Enterprise Voice. Isso afeta como o sistema lida com as chamadas para números não atribuídos.
ms.openlocfilehash: 831cb389a97ea45130875b76005aab2059cf08ab
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "23260136"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="d5773-104">Criar ou excluir um anúncio no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d5773-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="d5773-105">Criar ou excluir comunicados para o aplicativo de anúncio no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d5773-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="d5773-106">Isso afeta como o sistema lida com as chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="d5773-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="d5773-p103">Ao configurar comunicados, na verdade você está configurando como deseja manipular as chamadas para números não atribuídos. É possível reproduzir um prompt, que pode ser um arquivo de áudio ou um arquivo TTS (conversão de texto em fala) ou simplesmente transferir a chamada para um destino especificado sem reproduzir um prompt.</span><span class="sxs-lookup"><span data-stu-id="d5773-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="d5773-p104">Você precisa criar anúncios antes de definir a tabela de números não atribuídos. Você precisa executar esta etapa para todos os anúncios que usam um prompt de áudio, de TTS ou nenhum prompt.</span><span class="sxs-lookup"><span data-stu-id="d5773-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="d5773-111">Este tópico descreve como importar e criar comunicados.</span><span class="sxs-lookup"><span data-stu-id="d5773-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="d5773-112">Para obter detalhes sobre como atribuir comunicados na tabela de números não atribuído, consulte [Configurar a tabela de número não atribuído](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="d5773-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="d5773-113">Criar um novo comunicado para números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="d5773-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="d5773-114">Para criar um novo comunicado, é necessário executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d5773-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="d5773-115">Para prompts de áudio, grave o arquivo de áudio usando seu aplicativo de gravação de áudio favorito.</span><span class="sxs-lookup"><span data-stu-id="d5773-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="d5773-116">Para prompts de áudio, execute o cmdlet **Import-CsAnnouncementFile** para importar o conteúdo do arquivo de áudio para o repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d5773-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="d5773-117">Execute o cmdlet **New-CsAnnouncement** , para criar e nomear o comunicado.</span><span class="sxs-lookup"><span data-stu-id="d5773-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="d5773-118">Execute esta etapa para criar comunicados com um prompt de áudio, um prompt TTS (text-to-speech), ou sem prompt.</span><span class="sxs-lookup"><span data-stu-id="d5773-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="d5773-119">Pode ser desejável criar um comunicado sem prompt (por exemplo, se você deseja transferir chamadas para um destino específico sem reproduzir uma mensagem).</span><span class="sxs-lookup"><span data-stu-id="d5773-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="d5773-120">Atribua o novo comunicado a um intervalo numérico na tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="d5773-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="d5773-121">Para criar um novo comunicado</span><span class="sxs-lookup"><span data-stu-id="d5773-121">To create a new announcement</span></span>

1. <span data-ttu-id="d5773-122">Para prompts de áudio, crie o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="d5773-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="d5773-123">Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="d5773-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="d5773-124">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="d5773-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="d5773-125">Para prompts de áudio, execute:</span><span class="sxs-lookup"><span data-stu-id="d5773-125">For audio prompts, run:</span></span>

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="d5773-126">Execute:</span><span class="sxs-lookup"><span data-stu-id="d5773-126">Run:</span></span>

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="d5773-p107">Para transferir chamadas para a caixa postal, digite o SIPAddress no formato sip:nomedousuário@nomedodomínio;opaque=app:voicemail (por exemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir chamadas para um número de telefone, digite o SIPAddress no formato sip:número@nomedodomínio;user=phone (por exemplo, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="d5773-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="d5773-129">Por exemplo, para especificar um prompt de áudio:</span><span class="sxs-lookup"><span data-stu-id="d5773-129">For example, to specify an audio prompt:</span></span>

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="d5773-130">Por exemplo, para especificar um prompt TTS:</span><span class="sxs-lookup"><span data-stu-id="d5773-130">For example, to specify a TTS prompt:</span></span>

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  <span data-ttu-id="d5773-131">Para obter mais detalhes sobre esses cmdlets e para ver uma lista dos códigos de idioma a ser usado no parâmetro **TextToSpeechPrompt** , consulte [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d5773-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="d5773-132">Excluir um comunicado para números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="d5773-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="d5773-133">Para excluir um anúncio</span><span class="sxs-lookup"><span data-stu-id="d5773-133">To delete an announcement</span></span>

1. <span data-ttu-id="d5773-134">Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="d5773-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="d5773-135">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="d5773-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d5773-p108">Lista todos os anúncios em sua organização. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d5773-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="d5773-p109">Na lista resultante, localize o anúncio que deseja excluir e copie o GUID. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d5773-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="d5773-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5773-140">For example:</span></span>

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="d5773-141">Para obter detalhes sobre mais opções, consulte [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) e [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d5773-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5773-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d5773-142">See also</span></span>

[<span data-ttu-id="d5773-143">Criar ou excluir um anúncio no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d5773-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="d5773-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="d5773-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="d5773-145">New-CsAnnouncement.</span><span class="sxs-lookup"><span data-stu-id="d5773-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="d5773-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="d5773-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="d5773-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="d5773-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

