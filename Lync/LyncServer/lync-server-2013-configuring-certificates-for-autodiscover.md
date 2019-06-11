---
title: 'Lync Server 2013: Configurando certificados para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Configurando certificados para descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-12_

Os certificados para o seu pool de directors, o pool de front-end e o proxy reverso exigem entradas de nomes alternativos de entidades adicionais para dar suporte a conexões seguras com clientes do Lync.

<div>


> [!NOTE]  
> Você pode usar o cmdlet <STRONG>Get-CsCertificate</STRONG> para exibir informações sobre os certificados atribuídos no momento. No entanto, o modo de exibição padrão trunca as propriedades do certificado e não exibe todos os valores na propriedade SubjectAlternativeNames. Você pode usar os cmdlets <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate e <STRONG>set-CsCertificate</STRONG> para ver algumas informações e solicitar e atribuir certificados. No entanto, esse não é o melhor método para usar se você não tiver certeza das propriedades dos nomes alternativos da entidade (SAN) no certificado atual. Para exibir o certificado e todos os membros da propriedade, é recomendável usar o snap-in de certificados no <EM>console de gerenciamento Microsoft (MMC)</EM> ou usar o assistente de implantação do Lync Server. No assistente de implantação do Lync Server, você pode usar o assistente de certificado para exibir as propriedades do certificado. Os procedimentos para exibir, solicitar e atribuir um certificado usando o Shell de gerenciamento do Lync Server e o <EM>console de gerenciamento Microsoft (MMC)</EM> são detalhados nos procedimentos a seguir. Para usar o assistente de implantação do Lync Server, consulte os detalhes aqui se você implantou o director opcional ou o pool de directors: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurar certificados para o diretor no Lync Server 2013</A>. Para o servidor front-end ou o pool de front-end, consulte os detalhes aqui: <A href="lync-server-2013-configure-certificates-for-servers.md">configurar certificados para servidores no Lync Server 2013</A>.<BR>As etapas iniciais deste procedimento são etapas de preparação, para orientar você sobre qual função os certificados atuais são reproduzidos. Por padrão, os certificados não terão um lyncdiscover. &lt;sipdomain&gt; ou lyncdiscoverinternal. &lt;nome&gt; de domínio interno, a menos que você tenha instalado serviços de mobilidade anteriormente ou prepare seus certificados com antecedência. Este procedimento usa o nome de domínio SIP ' contoso.com ' de exemplo e o nome de domínio interno ' contoso.net '.<BR>A configuração de certificado padrão do Lync Server 2013 e do Lync Server 2010 é usar um único certificado (chamado ' default ') com o propósito padrão (para todas as finalidades, exceto para os serviços Web), WebServicesExternal e WebServicesInternal. Uma configuração opcional é usar certificados separados para cada finalidade. Os certificados podem ser gerenciados usando o Shell de gerenciamento do Lync Server e cmdlets do Windows PowerShell ou usando o assistente de certificado no assistente de implantação do Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para atualizar certificados com nomes alternativos de novos assuntos usando o Shell de gerenciamento do Lync Server

1.  Faça logon no computador usando uma conta que tenha direitos e permissões de administrador local.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Descubra quais certificados foram atribuídos ao servidor e para qual tipo de uso. Você precisará destas informações na etapa seguinte para atribuir o certificado atualizado. Na linha de comando, digite:
    
        Get-CsCertificate

4.  Examine a saída da etapa anterior para ver se um único certificado está atribuído para vários usos ou se um certificado diferente está atribuído para cada uso. Examine o parâmetro use para descobrir como um certificado é usado. Compare o parâmetro de impressão digital para os certificados exibidos para ver se o mesmo certificado tem vários usos.

5.  Atualize o certificado. Na linha de comando, digite:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por exemplo, se o cmdlet **Get-CsCertificate** tiver exibido um certificado com uso do padrão, outro com um uso de WebServicesInternal e outro com um uso de WebServicesExternal, e todos tiverem o mesmo valor de impressão digital, na linha de comando, digite:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante: **
    
    Se um certificado separado for atribuído para cada uso (o valor de impressão digital for diferente para cada certificado), é importante que você não execute o cmdlet **set-CsCertificate** com vários tipos. Nesse caso, execute o cmdlet **set-CsCertificate** separadamente para cada uso. Por exemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para exibir o certificado, clique em **Iniciar**, clique em **executar..**.. Digite MMC para abrir o console de gerenciamento Microsoft.

7.  No menu MMC, selecione **arquivo**, selecione **Adicionar/remover snap-in..**., selecione certificados. Clique em **Adicionar**. Quando solicitado, selecione **conta de computador**e clique em **Avançar**.

8.  Se o certificado estiver localizado neste computador, selecione **computador local**. Se o certificado estiver localizado em outro computador, selecione **outro computador**, digite o nome de domínio totalmente qualificado do computador ou clique em **procurar** em **digite o nome do objeto a ser selecionado**, digite o nome do computador. Clique em **verificar nomes**. Quando o nome do computador for resolvido, ele será sublinhado. Clique em **OK**e, em seguida, clique em **concluir**. Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se o certificado não aparecer no console, verifique se você não selecionou o usuário ou o serviço. Você deve selecionar computador ou não será possível localizar o certificado probper.

    
    </div>

9.  Para exibir as propriedades do certificado, expanda **certificados**, expanda **pessoal**e selecione **certificados**. Selecione o certificado a ser exibido, clique com o botão direito do mouse no certificado e selecione **abrir**.

10. No modo de exibição de **certificado** , selecione **detalhes**. Aqui, você pode selecionar o nome do assunto do certificado selecionando **assunto** e o nome da entidade atribuída e as propriedades associadas serão exibidas.

11. Para exibir os nomes alternativos da entidade atribuída, selecione **nome alternativo do assunto**. Todos os nomes alternativos de assunto atribuídos são exibidos. Os nomes alternativos de entidades encontrados na propriedade são do tipo **DNS Name** por padrão. Você deve ver os membros a seguir (todos eles devem ter nomes de domínio totalmente qualificados, conforme representado nos registros do host DNS (A ou, se IPv6 AAAA):
    
      - Nome do pool para este pool ou o nome do servidor único se não for um pool
    
      - Nome do servidor ao qual o certificado está atribuído
    
      - Registros de URL simples, geralmente se encontram e se interligarem
    
      - Serviços Web internos e serviços Web nomes externos (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas opções feitas no construtor de topologias e nas seleções de serviços Web do ridden.
    
      - Se já foi atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<registros\> sipdomain.
    
    O último item é o que você mais interessa – se houver uma entrada de SAN lyncdiscover e lyncdiscoverinternal.
    
    Depois que tiver essas informações, você poderá fechar o modo de exibição de certificado e o MMC.

12. Se for um serviço de descoberta automática, ou seja, o lyncdiscover. \>nome\> de domínio e lyncdiscoverinternal. \<nome\> do domínio (com base em se este for um certificado externo ou interno) o nome alternativo do requerente estiver ausente, e você estiver usando um único certificado padrão para os tipos padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver muitos domínios SIP, não será possível usar o novo parâmetro AllSipDomain. Em vez disso, você deve usar o parâmetro DomainName. Ao usar o parâmetro DomainName, você deve definir o FQDN dos registros lyncdiscoverinternal e lyncdiscover. Por exemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para atribuir o certificado, digite o seguinte:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Onde "impressão digital" é a impressão digital exibida para o certificado recém emitido.

13. Para obter um nome alternativo de assunto da descoberta automática ausente ao usar certificados separados para padrão, WebServicesInternal e WebServicesExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver muitos domínios SIP, não será possível usar o novo parâmetro AllSipDomain. Em vez disso, você deve usar o parâmetro DomainName. Ao usar o parâmetro DomainName, você deve usar um prefixo apropriado para o FQDN do domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para obter um nome alternativo de assunto de descoberta automática externo ausente, na linha de comando, digite:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver muitos domínios SIP, não será possível usar o novo parâmetro AllSipDomain. Em vez disso, você deve usar o parâmetro DomainName. Ao usar o parâmetro DomainName, você deve usar um prefixo apropriado para o FQDN do domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para atribuir os tipos de certificados individuais, digite o seguinte:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Em que "impressão digital" é a impressão digital exibida para os certificados individuais emitidos recentemente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

