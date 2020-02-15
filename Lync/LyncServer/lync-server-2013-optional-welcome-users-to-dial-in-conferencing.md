---
title: 'Lync Server 2013: (opcional) bem-vindo aos usuários de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4f4a7882c40095017d2678549edf618b78e29
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="e26a9-102">Opcion Usuários de boas-vindas para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e26a9-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e26a9-103">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e26a9-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e26a9-104">Depois de configurar a conferência discada e testar para verificar se está funcionando corretamente, você deve definir os números de identificação pessoal iniciais (PINs) para usuários e notificar os usuários sobre a disponibilidade do recurso, incluindo instruções introdutórias, como o PIN inicial e o link para a página da Web configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="e26a9-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="e26a9-105">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="e26a9-105">This step is optional.</span></span> <span data-ttu-id="e26a9-106">Normalmente, você usa o cmdlet **set-CsClientPin** para redefinir Pins, mas você pode usar o procedimento neste tópico pela primeira vez se quiser enviar um email de boas-vindas com as informações.</span><span class="sxs-lookup"><span data-stu-id="e26a9-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="e26a9-107">Se não quiser enviar o email, você pode usar **set-CsClientPin** em vez disso.</span><span class="sxs-lookup"><span data-stu-id="e26a9-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="e26a9-108">Você pode usar o script **set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="e26a9-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="e26a9-109">Por padrão, o script não redefine um PIN se já estiver definido, mas você pode usar o parâmetro **Force** para forçar a redefinição de um PIN.</span><span class="sxs-lookup"><span data-stu-id="e26a9-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="e26a9-110">A mensagem de email é enviada usando Simple Mail Transfer Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="e26a9-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="e26a9-111">Você pode criar um script que executa o script **set-CsPinSendCAWelcomeMail** iterativamente para definir Pins e enviar emails para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="e26a9-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="e26a9-112">Você pode modificar o modelo de email (ou seja, o arquivo **CAWelcomeEmailTemplate. html** ) para adicionar mais links a páginas da intranet ou modificar o texto do email.</span><span class="sxs-lookup"><span data-stu-id="e26a9-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="e26a9-113">Para definir um PIN inicial e enviar um email de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="e26a9-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="e26a9-114">Faça logon como membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e26a9-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e26a9-115">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e26a9-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e26a9-116">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="e26a9-116">Run the following at the command prompt:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
        -From <email address of sender> [-Subject <subject for email message>]
        [-UserEmailAddress <destination email address>]
        [-Cc <email address of recipients who receive copy of email>]
        [-Bcc <email address of recipients who receive blind copies>]
        [-TemplatePath <path for email template>]
        [-SmtpServer] <SMTP server name>]
        [-BodyAsPlainText] [-UseSsl]
        [-Pin <new numeric PIN>] [-Force] `
        [-Credential <SMTP server credentials used to send email with the specified From address>]
    
    <span data-ttu-id="e26a9-117">**SmtpServer**   por padrão, o script usa o valor da variável de ambiente reservada **$PSEmailServer** para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e26a9-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="e26a9-118">Se a variável **$PSEmailServer** não for definida, você deverá especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e26a9-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="e26a9-119">**Credencial**   por padrão, o script usa as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="e26a9-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="e26a9-120">Se o usuário atual não tiver permissão para enviar email em nome do endereço de origem especificado, você deverá especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e26a9-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="e26a9-121">Como regra geral, especifique esse parâmetro se não especificar seu endereço de email como o endereço do remetente.</span><span class="sxs-lookup"><span data-stu-id="e26a9-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="e26a9-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e26a9-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="e26a9-123">Este exemplo cria um novo PIN e envia um email de boas-vindas de Marco para Bob.</span><span class="sxs-lookup"><span data-stu-id="e26a9-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="e26a9-124">Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML.</span><span class="sxs-lookup"><span data-stu-id="e26a9-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="e26a9-125">O assunto padrão é "bem-vindo à conferência discada".</span><span class="sxs-lookup"><span data-stu-id="e26a9-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="e26a9-126">Outro exemplo:</span><span class="sxs-lookup"><span data-stu-id="e26a9-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="e26a9-127">Este exemplo força um novo PIN com um valor de "383042650" para Bob, embora Bob tivesse um PIN existente e envia um email de boas-vindas de Marco para Bob.</span><span class="sxs-lookup"><span data-stu-id="e26a9-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="e26a9-128">Como o parâmetro Credential é especificado, a pessoa que está executando o comando é solicitada a digitar uma senha.</span><span class="sxs-lookup"><span data-stu-id="e26a9-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="e26a9-129">O email é enviado usando o SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="e26a9-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

