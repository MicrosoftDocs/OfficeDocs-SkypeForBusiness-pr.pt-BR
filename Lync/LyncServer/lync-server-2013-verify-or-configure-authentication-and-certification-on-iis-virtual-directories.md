---
title: 'Lync Server 2013: verificar ou configurar autenticação e certificação nos diretórios virtuais do IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4a9e4b2ad53b3fa3a339eae7b4b1ee1f4412548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Verificar ou configurar a autenticação e certificação nos diretórios virtuais do IIS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-05-25_

Use o procedimento a seguir para configurar o certificado nos diretórios virtuais dos serviços de informações da Internet (IIS) ou verificar se o certificado está configurado corretamente. Execute o procedimento a seguir em cada servidor que executa o IIS em seu pool do Lync Server interno e no diretor opcional ou servidores do pool de diretores.

<div>


> [!NOTE]  
> O procedimento a seguir define um procedimento para solicitar um certificado combinado que é usado para todas as finalidades do Lync Server, site interno e site externo no IIS. O Lync Server 2010 introduziu um conjunto de cmdlets&nbsp;do Windows PowerShell do Shell de gerenciamento do Lync Server para o propósito expresso de gerenciamento de solicitação de certificado, importação e atribuição. O procedimento assume que há uma autoridade de certificação (CA) implantada internamente que pode processar a solicitação. Se você usar certificados públicos para fins do Lync Server ou sua autoridade de certificação exigir uma solicitação offline, consulte a sintaxe detalhada neste tópico para obter informações sobre o parâmetro – output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para configurar autenticação e certificados em diretórios virtuais de ISS

1.  Para concluir com êxito o seguinte, você deve estar conectado ao computador (servidor de front-end ou diretor) onde os serviços Web estão instalados e ser um administrador local. Você deve ter as permissões de **leitura** e **registrar** na autoridade de certificação que você estará solicitando certificados, caso a autoridade de certificação seja a sua organização. Você não precisa de permissões da autoridade de certificação se for configurar e enviar solicitações de certificado offline.

2.  Clique em **Iniciar**, selecione **Todos os programas**, selecione **Ferramentas administrativas** e, então, clique em **Gerenciador do Serviços de Informações da Internet (IIS)**.

3.  Em **Gerenciador do Serviços de Informações da Internet (IIS)**, selecione **ServerName**. Em **Exibição de recursos**, selecione **Certificados do servidor**, clique com o botão direito e selecione **Abrir recurso**.
    
    <div>
    

    > [!TIP]  
    > Na Exibição de recursos dos Certificados do servidor, caso haja certificados atribuídos ao servidor, eles aparecerão aí. Caso exista um certificado que corresponda aos requisitos para o External Web Site no IIS, você pode reutilizar tal certificado. Para visualizar um certificado, clique com o botão direito no certificado e selecione <STRONG>Visualizar…</STRONG>

    
    </div>

4.  No servidor de front-ends ou diretor que você está solicitando o certificado, clique em **Iniciar**, selecione **todos os programas**, selecione **Microsoft Lync Server 2013**e clique em **Shell de gerenciamento do Lync Server**.

5.  No Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Get-CsCertificate
    
    A saída é uma lista dos certificados que estão atualmente no servidor, no repositório de certificados do Pessoal do Computador. Observe que, no certificado combinado (isto é, onde por padrão os serviços da web internos e externos estão utilizando o mesmo certificado), você verá que a propriedade Uso estará populado com Padrão, WebServicesInternal and WebServicesExternal. Além disso, a propriedade Thumbprint será a mesma para cada um dos tipos de Uso. Um exemplo de saída de Get-CsCertificate é exibido neste exemplo:
    
    ![Get-CsCertificate informações sobre o status atual do scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate informações sobre o status atual do scert")

6.  No Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Onde o comando completo se parecerá com o seguinte exemplo:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Por padrão, o Request-CsCertificate irá popular o nome da entidade com o nome do pool ou servidor e irá popular entradas no nome de entidade alternativo com o servidor FQDN, o pool FQDN, Simple URL FQDNs e serviços da web internos e externos FQDNs. Isso é feito ao referenciar ao documento de topologia na sua implantação. Caso exista um valor faltando e você tenha especificado o parâmetro –Verbose, você será notificado de que os valores atuais e computados para os nomes alternativos são diferentes, mas não informará qual valor está faltando. É fornecido apenas o valor computado completo que o cmdlet referencia. Utilize a string de nomes alternativos computados na saída para solicitar novamente um novo certificado que incluirá todos os valores.

    
    </div>
    
    ![Saída da solicitação de CERT usando Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Saída da solicitação de CERT usando Request-CsCertifica")

7.  No Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Onde o comando completo se parecerá com o seguinte exemplo:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    A saída do cmdlet Set-CsCertificate mostrará que o mesmo certificado (identificado pelo thumbprint do certificado) é atribuído para utilização Padrão, WebServicesExternal e WebServicesInternal.
    
    ![Saída de Set-CsCertificate no IIS WebEx](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Saída de Set-CsCertificate no IIS WebEx")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para verificar ou configurar a autenticação e certificados em diretórios virtuais do IIS

1.  Clique em **Iniciar**, selecione **Todos os programas**, selecione **Ferramentas administrativas** e clique em **Gerenciador dos Serviços de Informações da Internet (IIS)**.

2.  No **Gerenciador dos serviços de informações da Internet (IIS)**, expanda **ServerName**e expanda **sites**.

3.  Clique com o botão direito do mouse em **Lync Server External Web Site** e clique em **Editar Ligações**

4.  Verifique se o https está associado à porta 4443 e clique em **https**.

5.  Selecione a entrada HTTPS, clique em **Editar**e verifique se a WebServicesExternalCertificate do Lync Server está associada a esse protocolo. Compare o thumbprint do cmdlet Set-CsCertificate para garantir que o certificado esperado está corretamente associado ao HTTPS.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

