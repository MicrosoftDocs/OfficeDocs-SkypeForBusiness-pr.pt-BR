---
title: Enviar e-mail de boas vindas discada usuários em Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Resumo: Saiba como receba os usuários conferência discada no Skype para Business Server.'
ms.openlocfilehash: 51c4dbc04b44cb33e27cbe09f22608836485e9ad
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898491"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Enviar e-mail de boas vindas discada usuários em Skype para Business Server
 
**Resumo:** Aprenda a receba os usuários conferência discada no Skype para Business Server.
  
Depois de configurar a conferência discada e de testar para verificar se ela está funcionando corretamente, defina PINs (números de identificação pessoal) para os usuários e notifique-os sobre a disponibilidade do recurso. Você pode incluir instruções introdutórias como o PIN inicial e o link para a página da Web de Configurações da Conferência Discada. 
  
Normalmente, você usar o cmdlet **Set-CsClientPin** para redefinir o PIN, mas você pode usar o procedimento neste tópico, se você deseja enviar um email de boas-vindas introdutório com as informações de PIN. Se você não quiser enviar o email, pode usar **Set-CsClientPin**.
  
É possível usar o script **Set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário. Por padrão, o script não redefine um PIN se ele já estiver definido, mas é possível usar o parâmetro Force para forçar a redefinição de um PIN. A mensagem de email é enviada usando o protocolo SMTP (Simple Mail Transfer Protocol).
  
É possível criar um script que executa o script **Set-CsPinSendCAWelcomeMail** iterativamente a fim de definir PINs e enviar email a um grupo de usuários. É possível modificar o modelo de email (ou seja, o arquivo CAWelcomeEmailTemplate.html) para adicionar mais links às páginas da intranet ou modificar o texto do email.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Definir um PIN inicial e enviar um email de boas vindas

1. Faça logon como membro do grupo RTCUniversalServerAdmins.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
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

**SmtpServer** Por padrão, o script usa o valor do ambiente reservadas variável **$PSEmailServer** para esse parâmetro. Se a variável  **$PSEmailServer** não for definida, será necessário especificar esse parâmetro.
    
**Credencial** Por padrão, o script usa as credenciais do usuário atual. Se o usuário atual não tiver permissão para enviar email em nome do endereço do remetente, será necessário especificar esse parâmetro. Como regra geral, especifique esse parâmetro se você não especificar seu endereço de email como o endereço do remetente.
    
O exemplo a seguir cria um novo PIN e envia um email de boas-vindas de Marco para Bob. Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML. O Assunto padrão é "Bem-vindo à conferência discada".
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

O próximo exemplo força um novo PIN com um valor de "383042650" para Bob, embora Bob já tivesse um PIN existente, e envia um email de boas-vindas de Marco para Bob. Como o parâmetro Credential é especificado, a pessoa que está executando o comando recebe uma solicitação para digitar uma senha. O email é enviado usando SSL (Secure Sockets Layer).
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
