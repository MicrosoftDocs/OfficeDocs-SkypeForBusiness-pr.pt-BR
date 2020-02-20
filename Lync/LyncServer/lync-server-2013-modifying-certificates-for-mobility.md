---
title: 'Lync Server 2013: modificando certificados para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138e4c442f482550160b3a836a2d3258b5273853
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modificando certificados para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-20_

Para dar suporte a conexões seguras entre seu ambiente do Lync e seus clientes móveis, os certificados SSL (Secure Socket Layer) para seu pool de diretores, pool de front-ends e proxy reverso precisarão ser atualizados com algum nome alternativo de entidade adicional ( SAN). Se você precisar fazer o check-out de mais detalhes sobre os requisitos de certificado para mobilidade, confira a seção requisitos de certificado em [requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mas, basicamente, você precisará obter novos certificados da autoridade de certificação com as entradas San adicionais incluídas e, em seguida, adicionar esses certificados usando as etapas deste artigo.

Naturalmente, antes de começar, é uma boa ideia saber quais nomes alternativos de entidade seus certificados já têm. Se você não tiver certeza sobre o que já foi configurado, há várias maneiras de descobrir. Enquanto a opção para executar o **Get-CsCertificate** e outros comandos do PowerShell para exibir essas informações, (que percorremos abaixo) por padrão, esses dados serão truncados, portanto, você pode não ver todas as propriedades necessárias. Para obter uma boa visão do certificado e de todas as suas propriedades, você pode ir para o console de gerenciamento Microsoft (MMC) e carregar o snap-in de certificados (que também percorremos abaixo), ou você pode simplesmente verificar o assistente de implantação do Lync Server.

Conforme observado acima, as etapas a seguir vão orientá-lo na atualização dos certificados usando o Shell de gerenciamento do Lync Server e o MMC. Se você estiver interessado em usar o assistente de certificado no assistente de implantação do Lync Server para isso, você pode verificar [configurar certificados para o diretor no Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para o diretor ou pool de diretor, se você configurou um (talvez você não tenha). Para o servidor front-end ou o pool de front-ends, convém ver [configurar certificados para servidores no Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Uma última coisa a ter em mente é que você pode ter um único certificado padrão no seu ambiente do Lync Server 2013 ou pode ter certificados separados para o padrão (que é tudo, exceto os serviços Web), WebServicesExternal e WebServicesInternal. Seja qual for a configuração, essas etapas devem ajudá-lo.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para atualizar certificados com nomes alternativos de novos requerentes usando o Shell de gerenciamento do Lync Server

1.  Você precisa fazer logon no seu servidor do Lync Server 2013 usando uma conta que tenha direitos e permissões de administrador local. Além disso, se você estiver executando o PowerShell **Request-CsCertificate** nas etapas 12 e posteriores, a conta precisará ter direitos para a CA (autoridade de certificação) especificada.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Antes de poder atribuir um certificado atualizado, você precisará descobrir quais certificados foram atribuídos ao servidor e para qual tipo de uso. Na linha de comando, digite:
    
        Get-CsCertificate

4.  Revise a saída da etapa anterior para ver se um único certificado foi atribuído para vários usos ou se um certificado diferente foi atribuído para cada uso. Procure no parâmetro use para descobrir como o certificado está sendo usado. Compare o parâmetro Thumbprint dos certificados exibidos para ver se o mesmo certificado tem vários usos. Mantenha seus olhos no parâmetro Thumbprint.

5.  Atualize o certificado. Na linha de comando, digite:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por exemplo, se o cmdlet **Get-CsCertificate** exibiu um certificado com o uso de Default, outro com um uso de WebServicesInternal e outro com um uso de WebServicesExternal e todos tinham o mesmo valor de impressão digital, na linha de comando, você deverá digitar:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Se um certificado separado for atribuído para cada uso (de modo que o valor de impressão digital que você verificou acima seja diferente para cada certificado), é vital que você **não** execute o cmdlet **set-CsCertificate** com vários tipos, como no exemplo acima. Nesse caso, execute o cmdlet **Set-CsCertificate** separadamente para cada uso. Por exemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para exibir o certificado (ou certificados), clique em **Iniciar**, clique em **executar...**. Digite MMC para abrir o Console de Gerenciamento Microsoft.

7.  No menu do MMC, selecione **Arquivo**, selecione**Adicionar/Remover snap-in…**, selecione Certificados. Clique em **Adicionar**. Quando lhe for solicitado, selecione **Conta do computador** e, em seguida, clique em **Avançar**.

8.  Se este for o servidor onde o certificado está localizado, selecione **computador local**. Se o certificado estiver localizado em outro computador, selecione **outro computador**e, em seguida, digite o nome de domínio totalmente qualificado do computador ou clique em **procurar** em **Insira o nome do objeto a ser selecionado**e digite o nome do computador. Clique em **Verificar Nomes**. Quando o nome do computador resolver, ele será sublinhado. Clique em **OK**e em **concluir**. Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .

9.  Para exibir as propriedades do certificado, expanda **Certificados**, expanda **Pessoal** e selecione **Certificados**. Selecione o certificado para exibição, clique com o botão direito do mouse em certificado e selecione **Abrir**.

10. Na exibição **Certificado**, selecione **Detalhes**. Aqui, você pode escolher o nome da entidade do certificado ao selecionar **Assunto** e o nome da entidade atribuída e as propriedades atribuídas serão exibidos.

11. Para exibir os nomes alternativos de entidades atribuídos, selecione**Nome Alternativo de Entidade**. Todos os nomes alternativos de entidade atribuídos são exibidos aqui. Os nomes alternativos da entidade encontrados aqui são do tipo **nome DNS** por padrão. Você deve ver os seguintes membros (todos deveriam ser nomes de domínio completamente qualificados) como representado nos registros de host DNS (A ou, se IPv6, AAAA):
    
      - Nome do pool para este pool ou o nome do servidor único se não for um pool
    
      - Nome do servidor ao qual o certificado está atribuído
    
      - Registros de URL Simples, normalmente reunir e discar
    
      - Nomes internos e externos de serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no construtor de topologias e nas seleções de serviços Web do nas.
    
      - Se já tiver sido atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros.
    
    O último item é o que você está mais interessado, se houver uma entrada de SAN do lyncdiscover e do lyncdiscoverinternal.
    
    Repita essas etapas se você tiver vários certificados para verificar. Assim que obtiver essa informação, você pode fechar o certificado exibido e o MMC.

12. Se um nome alternativo de entidade do serviço Descoberta Automática estiver ausente, e você está usando um certificado Padrão para os tipos Padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver vários domínios SIP, não poderá usar o novo parâmetro AllSipDomain. Em vez disso, você precisa usar o parâmetro DomainName. Quando você usa o parâmetro DomainName, você precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Por exemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para atribuir o certificado, digite o seguinte:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Onde “Thumbprint” é o thumbprint exibido para o novo certificado emitido.

13. Para uma SAN interna de descoberta automática ausente ao usar certificados separados para padrão, WebServicesInternal e WebServicesExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver vários domínios SIP, não poderá usar o novo parâmetro AllSipDomain. Em vez disso, você precisa usar o parâmetro DomainName. Quando você usa o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para obter um nome alternativo da entidade de Descoberta Automática externo, digite na linha de comando:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver vários domínios SIP, não poderá usar o novo parâmetro AllSipDomain. Em vez disso, você precisa usar o parâmetro DomainName. Quando você usa o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para atribuir os tipos de certificados individuais, digite o seguinte:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Onde “Thumbprint” é o thumbprint exibido para os novos certificados individuais emitidos.
    
    <div>
    

    > [!NOTE]  
    > Apenas para observar, as etapas 12 e 13 devem ser executadas somente se a conta que a executa tiver acesso à autoridade de certificação com as permissões apropriadas. Se você não conseguir fazer logon com uma conta que tenha essas permissões ou se estiver usando uma autoridade de certificação pública ou remota para seus certificados, precisará solicitá-las por meio do assistente de implantação do Lync Server, que foi tocado na parte superior da segue.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

