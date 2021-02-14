---
title: Enviar um email de boas-vindas para usuários de discagem no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Resumo: Saiba como dar as boas-vindas aos usuários na conferência discada no Skype for Business Server.'
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817491"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="7999b-103">Enviar um email de boas-vindas para usuários de discagem no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7999b-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="7999b-104">**Resumo:** Saiba como dar as boas-vindas aos usuários na conferência discada no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7999b-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="7999b-105">Depois de configurar a conferência discada e testar para verificar se ela está funcionando corretamente, você deve definir os piNs (números de identificação pessoal) iniciais para os usuários e notificar os usuários sobre a disponibilidade do recurso.</span><span class="sxs-lookup"><span data-stu-id="7999b-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="7999b-106">Você pode incluir instruções introdutórios, como o PIN inicial e o link para a página da Web de Configurações de Conferência Discar.</span><span class="sxs-lookup"><span data-stu-id="7999b-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="7999b-107">Normalmente, você usa o cmdlet **Set-CsClientPin** para redefinir PINs, mas pode usar o procedimento neste tópico se quiser enviar um email de boas-vindas introdutório com as informações de PIN.</span><span class="sxs-lookup"><span data-stu-id="7999b-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="7999b-108">Se você não quiser enviar o email, poderá usar **Set-CsClientPin.**</span><span class="sxs-lookup"><span data-stu-id="7999b-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="7999b-109">Você pode usar o script **Set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="7999b-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="7999b-110">Por padrão, o script não redefine um PIN se ele já estiver definido, mas você pode usar o parâmetro Force para forçar a redefinição de um PIN.</span><span class="sxs-lookup"><span data-stu-id="7999b-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="7999b-111">A mensagem de email é enviada usando SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="7999b-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="7999b-112">Você pode criar um script que executa o script **Set-CsPinSendCAWelcomeMail** iterativamente para definir PINs e enviar emails para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="7999b-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="7999b-113">Você pode modificar o modelo de email (ou seja, o arquivo CAWelcomeEmailTemplate.html) para adicionar mais links às páginas da intranet ou modificar o texto do email.</span><span class="sxs-lookup"><span data-stu-id="7999b-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="7999b-114">Definir um PIN inicial e enviar um email de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="7999b-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="7999b-115">Faça logoff como membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7999b-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="7999b-116">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="7999b-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7999b-117">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="7999b-117">Run the following at the command prompt:</span></span>
    
   ```PowerShell
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
   ```

<span data-ttu-id="7999b-118">**SmtpServer** Por padrão, o script usa o valor da variável de ambiente **reservado $PSEmailServer** para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7999b-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="7999b-119">Se a **$PSEmailServer** variável não estiver definida, você deverá especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7999b-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="7999b-120">**Credencial** Por padrão, o script usa as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="7999b-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="7999b-121">Se o usuário atual não tiver permissão para enviar emails em nome do endereço De especificado, especifique esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7999b-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="7999b-122">Como regra geral, especifique esse parâmetro se você não especificar seu endereço de email como o endereço De.</span><span class="sxs-lookup"><span data-stu-id="7999b-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="7999b-123">O exemplo a seguir cria um novo PIN e envia um email de boas-vindas de Marco para Bob.</span><span class="sxs-lookup"><span data-stu-id="7999b-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="7999b-124">Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML.</span><span class="sxs-lookup"><span data-stu-id="7999b-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="7999b-125">O assunto padrão é "Bem-vindo à conferência discda":</span><span class="sxs-lookup"><span data-stu-id="7999b-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="7999b-126">O próximo exemplo força um novo PIN com o valor "383042650" para Bob, mesmo que Bob tenha um PIN existente e envia um email de boas-vindas de Marco para Bob.</span><span class="sxs-lookup"><span data-stu-id="7999b-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="7999b-127">Como o parâmetro Credential é especificado, a pessoa que executa o comando é solicitado a inserir uma senha.</span><span class="sxs-lookup"><span data-stu-id="7999b-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="7999b-128">O email é enviado usando o SSL (Secure Sockets Layer):</span><span class="sxs-lookup"><span data-stu-id="7999b-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
