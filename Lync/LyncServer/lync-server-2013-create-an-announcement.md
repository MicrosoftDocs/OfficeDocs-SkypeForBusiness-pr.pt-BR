---
title: 'Lync Server 2013: criar um anúncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50db03b8c6d428322129f1a46a0ffe50b19ed25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="dea6a-102">Criar um comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dea6a-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dea6a-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dea6a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dea6a-104">Para criar um novo comunicado, é necessário executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="dea6a-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="dea6a-105">Para prompts de áudio, grave o arquivo de áudio usando seu aplicativo de gravação de áudio favorito.</span><span class="sxs-lookup"><span data-stu-id="dea6a-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="dea6a-106">Para prompts de áudio, execute o cmdlet **Import-CsAnnouncementFile** para importar o conteúdo do arquivo de áudio para o Repositório de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="dea6a-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="dea6a-107">Execute o cmdlet **New-CsAnnouncement** para criar e nomear o comunicado.</span><span class="sxs-lookup"><span data-stu-id="dea6a-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="dea6a-108">Execute esta etapa para criar comunicados com um prompt de áudio, um prompt TTS (text-to-speech), ou sem prompt.</span><span class="sxs-lookup"><span data-stu-id="dea6a-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="dea6a-109">Pode ser desejável criar um comunicado sem prompt (por exemplo, se você deseja transferir chamadas para um destino específico sem reproduzir uma mensagem).</span><span class="sxs-lookup"><span data-stu-id="dea6a-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="dea6a-110">Atribua o novo comunicado a um intervalo numérico na tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="dea6a-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="dea6a-111">Este tópico descreve como importar e criar comunicados.</span><span class="sxs-lookup"><span data-stu-id="dea6a-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="dea6a-112">Para obter detalhes sobre como atribuir comunicados na tabela de números não atribuídos, consulte [Configurar a tabela de números não atribuídos no Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="dea6a-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="dea6a-113">Para criar um novo comunicado</span><span class="sxs-lookup"><span data-stu-id="dea6a-113">To create a new announcement</span></span>

1.  <span data-ttu-id="dea6a-114">Para prompts de áudio, crie o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="dea6a-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="dea6a-115">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dea6a-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="dea6a-116">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dea6a-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="dea6a-117">Para prompts de áudio, execute:</span><span class="sxs-lookup"><span data-stu-id="dea6a-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="dea6a-118">Sejam</span><span class="sxs-lookup"><span data-stu-id="dea6a-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="dea6a-p103">Para transferir chamadas para a caixa postal, digite o SIPAddress no formato sip:nomedousuário@nomedodomínio;opaque=app:voicemail (por exemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir chamadas para um número de telefone, digite o SIPAddress no formato sip:número@nomedodomínio;user=phone (por exemplo, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="dea6a-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="dea6a-121">Por exemplo, para especificar um prompt de áudio:</span><span class="sxs-lookup"><span data-stu-id="dea6a-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="dea6a-122">Por exemplo, para especificar um prompt TTS:</span><span class="sxs-lookup"><span data-stu-id="dea6a-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="dea6a-123">Para obter mais detalhes sobre esses cmdlets e para ver uma lista dos códigos de idioma a serem usados no parâmetro **TextToSpeechPrompt** , consulte [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="dea6a-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dea6a-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="dea6a-124">See Also</span></span>


[<span data-ttu-id="dea6a-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="dea6a-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="dea6a-126">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="dea6a-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="dea6a-127">Configurar a tabela de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dea6a-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

