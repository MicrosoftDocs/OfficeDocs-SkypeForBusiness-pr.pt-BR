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
ms.openlocfilehash: d3a949d1de2c3237e1cd432297a1ce1e1a7f3543
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>Opcion Usuários de boas-vindas para conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-30_

Depois de configurar a conferência discada e testar para verificar se está funcionando corretamente, você deve definir os números de identificação pessoal iniciais (PINs) para usuários e notificar os usuários sobre a disponibilidade do recurso, incluindo instruções introdutórias, como o PIN inicial e o link para a página da Web configurações de conferência discada. Essa etapa é opcional. Normalmente, você usa o cmdlet **set-CsClientPin** para redefinir Pins, mas você pode usar o procedimento neste tópico pela primeira vez se quiser enviar um email de boas-vindas com as informações. Se não quiser enviar o email, você pode usar **set-CsClientPin** em vez disso.

Você pode usar o script **set-CsPinSendCAWelcomeMail** para definir o PIN e enviar um email de boas-vindas para um único usuário. Por padrão, o script não redefine um PIN se já estiver definido, mas você pode usar o parâmetro **Force** para forçar a redefinição de um PIN. A mensagem de email é enviada usando Simple Mail Transfer Protocol (SMTP).

Você pode criar um script que executa o script **set-CsPinSendCAWelcomeMail** iterativamente para definir Pins e enviar emails para um grupo de usuários. Você pode modificar o modelo de email (ou seja, o arquivo **CAWelcomeEmailTemplate. html** ) para adicionar mais links a páginas da intranet ou modificar o texto do email.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Para definir um PIN inicial e enviar um email de boas-vindas

1.  Faça logon como membro do grupo RTCUniversalServerAdmins.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

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
    
    **SmtpServer**   por padrão, o script usa o valor da variável de ambiente reservada **$PSEmailServer** para esse parâmetro. Se a variável **$PSEmailServer** não for definida, você deverá especificar esse parâmetro.
    
    **Credencial**   por padrão, o script usa as credenciais do usuário atual. Se o usuário atual não tiver permissão para enviar email em nome do endereço de origem especificado, você deverá especificar esse parâmetro. Como regra geral, especifique esse parâmetro se não especificar seu endereço de email como o endereço do remetente.
    
    Por exemplo:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    Este exemplo cria um novo PIN e envia um email de boas-vindas de Marco para Bob. Ele usa o texto de email do modelo padrão e cria a mensagem de email no formato HTML. O assunto padrão é "bem-vindo à conferência discada".
    
    Outro exemplo:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    Este exemplo força um novo PIN com um valor de "383042650" para Bob, embora Bob tivesse um PIN existente e envia um email de boas-vindas de Marco para Bob. Como o parâmetro Credential é especificado, a pessoa que está executando o comando é solicitada a digitar uma senha. O email é enviado usando o SSL (Secure Sockets Layer).

</div>

</div>

<span> </span>

</div>

</div>

</div>

