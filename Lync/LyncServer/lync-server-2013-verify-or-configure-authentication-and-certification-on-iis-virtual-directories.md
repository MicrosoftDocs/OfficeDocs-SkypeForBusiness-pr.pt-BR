---
title: 'Lync Server 2013: Verificar ou configurar autenticação e certificação nos diretórios virtuais de IIS'
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
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Verificar ou configurar autenticação e certificação nos diretórios virtuais de IIS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-05-25_

Use o procedimento a seguir para configurar o certificado nos diretórios virtuais dos serviços de informações da Internet (IIS) ou verificar se o certificado está configurado corretamente. Execute o procedimento a seguir em cada servidor que executa o IIS em seu pool interno do Lync Server e no director opcional. ou servidores do pool do diretor.

<div>


> [!NOTE]  
> O procedimento a seguir define um procedimento para solicitar um certificado combinado que é usado para todas as finalidades do Lync Server, site interno e site externo no IIS. O Lync Server 2010 introduziu um conjunto de cmdlets&nbsp;do shell do shell do Shell de gerenciamento do Lync Server para a finalidade expressa de gerenciamento de solicitação, importação e atribuição de certificado. O procedimento pressupõe que há uma autoridade de certificação (CA) implantada internamente que pode processar a solicitação. Se você usar certificados públicos para fins do Lync Server ou a autoridade de certificação exigir uma solicitação offline, consulte a sintaxe detalhada neste tópico para obter informações sobre o parâmetro – output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Solicitação-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para configurar a autenticação e certificados em diretórios virtuais do IIS

1.  Para concluir com êxito o seguinte, você deve estar conectado ao computador (servidor front-end ou diretor) em que os serviços Web estão instalados e ser um administrador local. Você deve ter as permissões de **leitura** e **registro** na autoridade de certificação da qual você solicitará certificados, se a autoridade de certificação for a autoridade de certificação da sua organização. Você não precisa de permissões para a autoridade de certificação se você irá configurar e enviar uma solicitação de certificado offline.

2.  Clique em **Iniciar**, selecione **todos os programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.

3.  No **Gerenciador dos serviços de informações da Internet (IIS)**, selecione **nomedoservidor**. No **modo de exibição recursos**, selecione **certificados de servidor**, clique com o botão direito do mouse e selecione **abrir recurso**.
    
    <div>
    

    > [!TIP]  
    > No modo de exibição de recursos de certificados do servidor, se houver certificados atribuídos ao servidor, eles serão exibidos aqui. Se houver um certificado que corresponda aos requisitos do site externo no IIS, você poderá reutilizar esse certificado. Para exibir um certificado, clique com o botão direito do mouse no certificado e selecione <STRONG>Exibir...</STRONG>

    
    </div>

4.  No servidor ou diretor de front-end para o qual você está solicitando o certificado, clique em **Iniciar**, selecione **todos os programas**, selecione **Microsoft Lync Server 2013**e clique em **Shell de gerenciamento do Lync Server**.

5.  No Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Get-CsCertificate
    
    A saída é uma lista dos certificados que estão atualmente no servidor no repositório de certificados do computador pessoal. Observe que, no certificado combinado (ou seja, em que o padrão, os serviços Web internos e os serviços Web externos estão usando o mesmo certificado), você verá que a propriedade use será preenchida com default, WebServicesInternal e WebServicesExternal. Além disso, a propriedade Thumbprint será a mesma para cada um dos tipos de uso. Um exemplo de saída de Get-CsCertificate é mostrado neste exemplo:
    
    ![Informações de Get-CsCertificate sobre o status atual do scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Informações de Get-CsCertificate sobre o status atual do scert")

6.  No Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Onde o comando completo seria exibido, como exemplo a seguir:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Por padrão, a solicitação-CsCertificate preencherá o nome do requerente com o nome do servidor ou do pool e preencherá as entradas no nome alternativo do requerente com o FQDN do servidor, FQDN do pool, FQDNs de URL simples e FQDNs de serviços Web internos e externos. Isso faz referência ao documento de topologia na sua implantação. Se houver um valor ausente e você tiver especificado o parâmetro – Verbose, você será notificado de que os valores calculados e reais para nomes alternativos são diferentes, mas ele não informa quais valores estão ausentes. Ele fornece o valor total calculado que o cmdlet referencia. Use a cadeia de caracteres de nomes alternativos calculados na saída para resolicitar um novo certificado que incluirá todos os valores.

    
    </div>
    
    ![Saída da solicitação de certificado usando Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Saída da solicitação de certificado usando Request-CsCertifica")

7.  No Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Onde o comando completo seria exibido, como exemplo a seguir:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    A saída do cmdlet Set-CsCertificate mostrará que o mesmo certificado (identificado pela impressão digital do certificado) é atribuído para o uso padrão, WebServicesExternal e WebServicesInternal.
    
    ![Saída de Set-CsCertificate no IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Saída de Set-CsCertificate no IIS WebExt")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Para verificar ou configurar a autenticação e os certificados nos diretórios virtuais do IIS

1.  Clique em **Iniciar**, selecione **todos os programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.

2.  No **Gerenciador dos serviços de informações da Internet (IIS)**, expanda **ServerName**e, em seguida, expanda **sites**.

3.  Clique com o botão direito do mouse **no site externo do Lync Server**e clique em **Editar associações**

4.  Verifique se HTTPS está associado à porta 4443 e clique em **https**.

5.  Selecione a entrada HTTPS, clique em **Editar**e verifique se o Lync Server WebServicesExternalCertificate está associado a esse protocolo. Compare a impressão digital do cmdlet Set-CsCertificate para garantir que o certificado esperado seja corretamente associado à associação HTTPS.

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

