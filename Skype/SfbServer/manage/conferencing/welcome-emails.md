---
title: Enviar emails de boas-vindas aos usuários discado no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Resumo: saiba como dar as boas-vindas aos usuários para conferência discar no Skype for Business Server.'
ms.openlocfilehash: 672e386c223e2b5b9f872334634ac315c9e900e1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848534"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Enviar emails de boas-vindas aos usuários discado no Skype for Business Server
 
**Resumo:** Saiba como dar as boas-vindas aos usuários para conferência discar em Skype for Business Server.
  
Depois de configurar a conferência discada e testar para verificar se ela está funcionando corretamente, você deve definir os PINs (números de identificação pessoal) iniciais para os usuários e notificar os usuários sobre a disponibilidade do recurso. Você pode incluir instruções introdutórios, como o PIN inicial e o link para a página da Web Configurações conferência discado. 
  
Normalmente, você usa o cmdlet **Set-CsClientPin** para redefinir PINs, mas pode usar o procedimento neste tópico se quiser enviar um email de boas-vindas introdutório com as informações de PIN. Se você não quiser enviar o email, poderá usar **Set-CsClientPin.**
  
Você pode usar o **script Set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário. Por padrão, o script não redefine um PIN se ele já estiver definido, mas você pode usar o parâmetro Force para forçar a redefinição de um PIN. A mensagem de email é enviada usando o Protocolo SMTP (Simple Mail Transfer Protocol).
  
Você pode criar um script que executa o script **Set-CsPinSendCAWelcomeMail** iterativamente para definir PINs e enviar emails para um grupo de usuários. Você pode modificar o modelo de email (ou seja, o arquivo CAWelcomeEmailTemplate.html) para adicionar mais links às páginas da intranet ou modificar o texto de email.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Definir um PIN inicial e enviar emails de boas-vindas

1. Faça logoff como membro do grupo RTCUniversalServerAdmins.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
3. Execute o seguinte no prompt de comando:
    
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

**SmtpServer** Por padrão, o script usa o valor da variável de ambiente **reservado $PSEmailServer** para esse parâmetro. Se a **$PSEmailServer** não estiver definida, você deverá especificar esse parâmetro.
    
**Credencial** Por padrão, o script usa as credenciais do usuário atual. Se o usuário atual não tiver permissão para enviar emails em nome do endereço From especificado, especifique esse parâmetro. Como regra geral, especifique esse parâmetro se você não especificar seu endereço de email como o endereço De.
    
O exemplo a seguir cria um novo PIN e envia um email de boas-vindas de Marco para Bob. Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML. O assunto padrão é "Bem-vindo à conferência discar":
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

O próximo exemplo força um novo PIN com um valor de "383042650" para Bob, mesmo que Bob tenha um PIN existente e envie um email de boas-vindas de Marco para Bob. Como o parâmetro Credential é especificado, a pessoa que executa o comando é solicitado a inserir uma senha. O email é enviado usando o SSL (Secure Sockets Layer):
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
