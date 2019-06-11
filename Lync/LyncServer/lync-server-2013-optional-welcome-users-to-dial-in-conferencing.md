---
title: 'Lync Server 2013: (Opcional) Dar as boas-vindas aos usuários na conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3defde18a01ed09ac529ba9b289749f28c4cdd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(Opcional) Dar as boas-vindas aos usuários na conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Depois de configurar a conferência discada e testar para verificar se ela está funcionando corretamente, você deve definir os números de identificação pessoal iniciais (PINs) para os usuários e notificar os usuários sobre a disponibilidade do recurso, incluindo instruções introdutórias, como o PIN inicial e o link para a página de configurações da conferência discada. Esta etapa é opcional. Geralmente, você usa o cmdlet **set-CsClientPin** para redefinir Pins, mas você pode usar o procedimento neste tópico da primeira vez se quiser enviar um email de boas-vindas com as informações. Se você não quiser enviar o email, pode usar **Set-CsClientPin**.

É possível usar o script **Set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário. Por padrão, o script não redefine um PIN se já estiver definido, mas você pode usar o parâmetro **Force** para forçar a redefinição de um PIN. A mensagem de email é enviada usando o protocolo SMTP (Simple Mail Transfer Protocol).

É possível criar um script que executa o script **Set-CsPinSendCAWelcomeMail** iterativamente a fim de definir PINs e enviar email a um grupo de usuários. Você pode modificar o modelo de email (ou seja, o arquivo **CAWelcomeEmailTemplate. html** ) para adicionar mais links a páginas da intranet ou modificar o texto do email.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Para definir um PIN inicial e enviar um email de boas-vindas

1.  Faça logon como membro do grupo RTCUniversalServerAdmins.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute o seguinte no prompt de comando:
    
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
    
    **SmtpServer**   por padrão, o script usa o valor da variável de ambiente reservada **$PSEmailServer** para esse parâmetro. Se a variável  **$PSEmailServer** não for definida, será necessário especificar esse parâmetro.
    
    **Credencial**   por padrão, o script usa as credenciais do usuário atual. Se o usuário atual não tiver permissão para enviar email em nome do endereço do remetente, será necessário especificar esse parâmetro. Como regra geral, especifique esse parâmetro se você não especificar seu endereço de email como o endereço do remetente.
    
    Por exemplo:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    Este exemplo cria um novo PIN e envia um email de boas-vindas de Marco para Bob. Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML. O assunto padrão é "bem-vindo à conferência discada".
    
    Outro exemplo:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    Este exemplo força um novo PIN com um valor de "383042650" para Bob, mesmo que Bob tivesse um pino existente e, em seguida, envia um email de boas-vindas de Marco para Bob. Como o parâmetro Credential é especificado, a pessoa que está executando o comando recebe uma solicitação para digitar uma senha. O email é enviado usando-se o Secure Sockets Layer (SSL).

</div>

</div>

<span> </span>

</div>

</div>

</div>

