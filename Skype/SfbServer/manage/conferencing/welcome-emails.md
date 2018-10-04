---
title: Enviar e-mail de boas vindas discada usuários em Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Resumo: Saiba como receba os usuários conferência discada no Skype para Business Server.'
ms.openlocfilehash: 90c56fd97d9eb51c96c1a0cb149f732a31a70743
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373710"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="ebd1a-103">Enviar e-mail de boas vindas discada usuários em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ebd1a-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="ebd1a-104">**Resumo:** Aprenda a receba os usuários conferência discada no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="ebd1a-105">Depois de configurar a conferência discada e de testar para verificar se ela está funcionando corretamente, defina PINs (números de identificação pessoal) para os usuários e notifique-os sobre a disponibilidade do recurso.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="ebd1a-106">Você pode incluir instruções introdutórias como o PIN inicial e o link para a página da Web de Configurações da Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="ebd1a-107">Normalmente, você usar o cmdlet **Set-CsClientPin** para redefinir o PIN, mas você pode usar o procedimento neste tópico, se você deseja enviar um email de boas-vindas introdutório com as informações de PIN.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="ebd1a-108">Se você não quiser enviar o email, pode usar **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="ebd1a-p103">É possível usar o script **Set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário. Por padrão, o script não redefine um PIN se ele já estiver definido, mas é possível usar o parâmetro Force para forçar a redefinição de um PIN. A mensagem de email é enviada usando o protocolo SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="ebd1a-p103">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user. By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN. The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="ebd1a-p104">É possível criar um script que executa o script **Set-CsPinSendCAWelcomeMail** iterativamente a fim de definir PINs e enviar email a um grupo de usuários. É possível modificar o modelo de email (ou seja, o arquivo CAWelcomeEmailTemplate.html) para adicionar mais links às páginas da intranet ou modificar o texto do email.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-p104">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users. You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="ebd1a-114">Definir um PIN inicial e enviar um email de boas vindas</span><span class="sxs-lookup"><span data-stu-id="ebd1a-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="ebd1a-115">Faça logon como membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ebd1a-116">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ebd1a-117">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ebd1a-117">Run the following at the command prompt:</span></span>
    
   ```
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

<span data-ttu-id="ebd1a-118">**SmtpServer** Por padrão, o script usa o valor do ambiente reservadas variável **$PSEmailServer** para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="ebd1a-119">Se a variável **$PSEmailServer** não estiver definida, você deve especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="ebd1a-120">**Credencial** Por padrão, o script usa as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="ebd1a-121">Se o usuário atual não tiver permissão para enviar email em nome do endereço do remetente, será necessário especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="ebd1a-122">Como regra geral, especifique esse parâmetro se você não especificar seu endereço de email como o endereço do remetente.</span><span class="sxs-lookup"><span data-stu-id="ebd1a-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="ebd1a-p107">O exemplo a seguir cria um novo PIN e envia um email de boas-vindas de Marco para Bob. Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML. O Assunto padrão é "Bem-vindo à conferência discada".</span><span class="sxs-lookup"><span data-stu-id="ebd1a-p107">The following example creates a new PIN, and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="ebd1a-p108">O próximo exemplo força um novo PIN com um valor de "383042650" para Bob, embora Bob já tivesse um PIN existente, e envia um email de boas-vindas de Marco para Bob. Como o parâmetro Credential é especificado, a pessoa que está executando o comando recebe uma solicitação para digitar uma senha. O email é enviado usando SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="ebd1a-p108">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```