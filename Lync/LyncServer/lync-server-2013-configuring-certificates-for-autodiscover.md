---
title: 'Lync Server 2013: Configurando certificados para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502108"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configurando certificados para descoberta automática no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-12_

Os certificados do seu pool de diretores, pool de front-ends e proxy reverso exigem entradas de nome alternativo de entidade adicional para dar suporte a conexões seguras com clientes Lync.

<div>


> [!NOTE]  
> Você pode usar o cmdlet <STRONG>Get-CsCertificate</STRONG> para exibir as informações sobre os certificados atualmente atribuídos. No entanto, o modo padrão trunca as propriedades do certificado e não exibe todos os valores na propriedade SubjectAlternativeNames. Você pode usar o <STRONG>Get-CsCertificate</STRONG> , o CsCertificate <STRONG>Request-</STRONG> e os cmdlets <STRONG>Set-CsCertificate</STRONG> para exibir alguma informação e para solicitar e atribuir certificados. Porém, não é o melhor método a ser usado se você não conhece as propriedades do SAN (nomes alternativos da entidade) no certificado atual. Para exibir o certificado e todos os membros de propriedade, é recomendável usar o snap-in de certificados no <EM>console de gerenciamento Microsoft (MMC)</EM> ou usar o assistente de implantação do Lync Server. No assistente de implantação do Lync Server, você pode usar o assistente de certificado para exibir as propriedades do certificado. Os procedimentos para exibir, solicitar e atribuir um certificado usando o Shell de gerenciamento do Lync Server e o <EM>MMC (console de gerenciamento Microsoft)</EM> são detalhados nos procedimentos a seguir. Para usar o assistente de implantação do Lync Server, confira detalhes aqui se você tiver implantado o diretor opcional ou o pool de diretores: <A href="lync-server-2013-configure-certificates-for-the-director.md">configure certificados para o diretor no Lync Server 2013</A>. Para o servidor front-end ou o pool de front-ends, consulte os detalhes aqui: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure Certificates for Servers in Lync Server 2013</A>.<BR>As etapas iniciais nesse procedimento são de preparação para te orientar sobre a função do certificado atual. Por padrão, os certificados não terão lyncdiscover. &lt; sipdomain &gt; ou lyncdiscoverinternal. &lt; entrada de nome de domínio interno &gt; , a menos que você tenha instalado os serviços de mobilidade anteriormente ou tenha preparado os certificados com antecedência. Esse procedimento utiliza o exemplo do nome do domínio SIP ‘contoso.com’ e o exemplo do nome do domínio interno ‘contoso.net’.<BR>A configuração de certificado padrão do Lync Server 2013 e do Lync Server 2010 é usar um único certificado (chamado "padrão") com o padrão de finalidades (para todos os fins, exceto para os serviços Web), WebServicesExternal e WebServicesInternal. Uma configuração opcional seria usar certificados separados para cada propósito. Os certificados podem ser gerenciados usando o Shell de gerenciamento do Lync Server e os cmdlets do Windows PowerShell, ou usando o assistente de certificado no assistente de implantação do Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para atualizar certificados com nomes alternativos de novos requerentes usando o Shell de gerenciamento do Lync Server

1.  Faça logon no computador usando uma conta que tenha permissões e direitos de administrador local.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Descubra quais certificados foram atribuídos ao servidor e para qual tipo de uso. Você precisará dessas informações na próxima etapa para atribuir o certificado atualizado. Na linha de comando, digite:
    
        Get-CsCertificate

4.  Examine o resultado da etapa anterior para ver se um único certificado foi atribuído a vários usos ou se um certificado diferente foi atribuído para cada uso. Examine o parâmetro Use para descobrir como um certificado é usado. Compare o parâmetro Thumbprint dos certificados exibidos para ver se o mesmo certificado tem vários usos.

5.  Atualize o certificado. Na linha de comando, digite:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por exemplo, se o cmdlet **Get-CsCertificate** exibiu um certificado com Use de Default, outro com um Use de WebServicesInternal e outro com um Use de WebServicesExternal, e todos eles tinham o mesmo valor de Thumbprint, digite na linha de comando:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Quando é atribuído um certificado separado para cada uso (valor de Thumbprint é diferente para cada certificado), é importante que você não execute o cmdlet **Set-CsCertificate** com vários tipos. Nesse caso, execute o cmdlet **Set-CsCertificate** separadamente para cada uso. Por exemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para exibir o certificado, clique em **Iniciar**, clique em **Executar…**. Digite MMC para abrir o Console de Gerenciamento Microsoft.

7.  No menu do MMC, selecione **Arquivo**, selecione**Adicionar/Remover snap-in…**, selecione Certificados. Clique em **Adicionar**. Quando lhe for solicitado, selecione **Conta do computador** e, em seguida, clique em **Avançar**.

8.  Se o certificado estiver localizado no computador, selecione **computador local**. Se o certificado estiver localizado em outro computador, selecione **outro computador**, digite o nome de domínio totalmente qualificado do computador ou clique em **procurar** em **Insira o nome do objeto a ser selecionado**, digite o nome do computador. Clique em **Verificar Nomes**. Quando o nome do computador for resolvido, ele será sublinhado. Clique em **OK**e em **concluir**. Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se o certificado não aparecer no console, verifique se você não selecionou o usuário ou serviço. Você deve selecionar computador ou não será possível localizar o certificado probper.

    
    </div>

9.  Para exibir as propriedades do certificado, expanda **Certificados**, expanda **Pessoal** e selecione **Certificados**. Selecione o certificado para exibição, clique com o botão direito do mouse em certificado e selecione **Abrir**.

10. Na exibição **Certificado**, selecione **Detalhes**. Aqui, você pode escolher o nome da entidade do certificado ao selecionar **Assunto** e o nome da entidade atribuída e as propriedades atribuídas serão exibidos.

11. Para exibir os nomes alternativos de entidades atribuídos, selecione**Nome Alternativo de Entidade**. Todos os nomes alternativos de entidade atribuídos são exibidos. Os nomes alternativos de entidade encontrados na propriedade são do tipo **Nome DNS** por padrão. Você deve ver os seguintes membros (todos deveriam ser nomes de domínio completamente qualificados) como representado nos registros de host DNS (A ou, se IPv6, AAAA):
    
      - Nome do pool para esse pool ou um nome de servidor único se esse não for um pool
    
      - Nome do servidor ao qual o certificado está atribuído
    
      - Registros de URL Simples, normalmente reunir e discar
    
      - Nomes internos e externos de serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no construtor de topologias e nas seleções de serviços Web do nas.
    
      - Se já tiver sido atribuído, o lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> relatórios.
    
    O último item é o mais interessante – se houver uma entrada SAN lyncdiscover e lyncdiscoverinternal.
    
    Assim que obtiver essa informação, você pode fechar o certificado exibido e o MMC.

12. Se um serviço de descoberta automática, ou seja, o lyncdiscover. \> nome \> de domínio e lyncdiscoverinternal.\<domain name\> (baseado em se este é um certificado externo ou interno), o nome alternativo da entidade está ausente e você está usando um único certificado padrão para os tipos padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você possui vários domínios SIP, não é possível usar o novo parâmetro AllSipDomain. Em vez disso, você deve usar o parâmetro DomainName. Quando você usar o parâmetro DomainName, você deve definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Por exemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para atribuir o certificado, digite o seguinte:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Onde “Thumbprint” é o thumbprint exibido para o novo certificado emitido.

13. Para nomes alternativos de entidades de Descoberta Automática interna ausente quando usam certificados separados por Padrão, WebServicesInternale e WebServicesExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você possui vários domínios SIP, não é possível usar o novo parâmetro AllSipDomain. Ao invés, você deve usar o parâmetro DomainName. Quando utilizar o parâmetro DomainName, você deve usar um prefixo adequado para o FQDN de domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para obter um nome alternativo da entidade de Descoberta Automática externo, digite na linha de comando:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você possui vários domínios SIP, não é possível usar o novo parâmetro AllSipDomain. Ao invés, você deve usar o parâmetro DomainName. Quando utilizar o parâmetro DomainName, você deve usar um prefixo adequado para o FQDN de domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para atribuir os tipos de certificados individuais, digite o seguinte:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Onde “Thumbprint” é o thumbprint exibido para os novos certificados individuais emitidos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

