---
title: 'Lync Server 2013: Modificando certificados para mobilidade'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Modificando certificados para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-20_

Para dar suporte a conexões seguras entre seu ambiente do Lync e seus clientes móveis, os certificados SSL (Secure Socket Layer) para seu pool de diretor, pool de front-end e proxy reverso precisarão ser atualizados com alguns nomes alternativos adicionais para o assunto ( SAN). Se você precisar conferir mais detalhes sobre os requisitos de certificado para mobilidade, consulte a seção requisitos de certificado em [requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mas basicamente precisará obter novos certificados da autoridade de certificação com as entradas San adicionais incluídas e adicionar esses certificados usando as etapas deste artigo.

É claro que antes de começar, é uma boa ideia saber quais são os nomes alternativos de assunto que seus certificados já possuem. Se você não tiver certeza de que já foi configurado, há várias maneiras de descobrir. Embora a opção de executar o **Get-CsCertificate** e outros comandos do PowerShell para exibir essas informações (que mostramos abaixo) por padrão, os dados serão truncados, portanto, você pode não conseguir ver todas as propriedades necessárias. Para obter uma boa visão do certificado e de todas as suas propriedades, você pode ir para o console de gerenciamento Microsoft (MMC) e carregar o snap-in de certificados (que também percorremos abaixo), ou você pode simplesmente verificar o assistente de implantação do Lync Server.

Conforme observado acima, as etapas a seguir vão orientá-lo na atualização dos certificados usando o Shell de gerenciamento do Lync Server e o MMC. Se você tiver interesse em usar o assistente de certificado no assistente de implantação do Lync Server para isso, poderá verificar a opção [configurar certificados para o diretor no Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para o diretor ou o pool do diretor, se você configurou um (você pode não ter). Para o servidor front-end ou o pool de front-end, convém ver [configurar certificados para servidores no Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Uma última coisa a ter em mente é que você pode ter um único certificado padrão em seu ambiente do Lync Server 2013 ou pode ter certificados separados para o padrão (que é tudo, exceto os serviços Web), WebServicesExternal e WebServicesInternal. Seja qual for a sua configuração, essas etapas devem ajudá-lo.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Para atualizar certificados com nomes alternativos de novos assuntos usando o Shell de gerenciamento do Lync Server

1.  Você precisa fazer logon no seu servidor do Lync Server 2013 usando uma conta com direitos e permissões de administrador local. Além disso, se você estiver executando o **CsCertificate de solicitação** do PowerShell nas etapas 12 e posteriores, a conta precisará ter direitos para a autoridade de certificação (CA) especificada.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Antes de poder atribuir um certificado atualizado, você precisará descobrir quais certificados foram atribuídos ao servidor e para qual tipo de uso. Na linha de comando, digite:
    
        Get-CsCertificate

4.  Examine a saída da etapa anterior para ver se um único certificado foi atribuído para vários usos ou se um certificado diferente está atribuído para cada uso. Examine o parâmetro use para descobrir como um certificado está sendo usado. Compare o parâmetro de impressão digital para os certificados exibidos para ver se o mesmo certificado tem vários usos. Fique de olho no parâmetro impressão digital.

5.  Atualize o certificado. Na linha de comando, digite:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por exemplo, se o cmdlet **Get-CsCertificate** tiver exibido um certificado com uso do padrão, outro com um uso de WebServicesInternal e outro com um uso de WebServicesExternal, e todos tivessem o mesmo valor de impressão digital, na linha de comando, você deve digitar:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante: **
    
    Se um certificado separado for atribuído para cada uso (para que o valor de impressão digital que você verificou acima seja diferente para cada certificado), é fundamental que você **não** execute o cmdlet **set-CsCertificate** com vários tipos, como no exemplo acima. Nesse caso, execute o cmdlet **set-CsCertificate** separadamente para cada uso. Por exemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para exibir o certificado (ou certificados), clique em **Iniciar**, clique em **executar...**. Digite MMC para abrir o console de gerenciamento Microsoft.

7.  No menu MMC, selecione **arquivo**, selecione **Adicionar/remover snap-in..**., selecione certificados. Clique em **Adicionar**. Quando solicitado, selecione **conta de computador**e clique em **Avançar**.

8.  Se este for o servidor em que o certificado está localizado, selecione **computador local**. Se o certificado estiver localizado em outro computador, você deve selecionar **outro computador**e, em seguida, pode digitar o nome de domínio totalmente qualificado do computador ou clicar em **procurar** , em **digite o nome do objeto a ser selecionado**e digitar o nome do computador. Clique em **verificar nomes**. Quando o nome do computador resolver, ele estará sublinhado. Clique em **OK**e, em seguida, clique em **concluir**. Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .

9.  Para exibir as propriedades do certificado, expanda **certificados**, expanda **pessoal**e selecione **certificados**. Selecione o certificado a ser exibido, clique com o botão direito do mouse no certificado e selecione **abrir**.

10. No modo de exibição de **certificado** , selecione **detalhes**. Aqui, você pode selecionar o nome do assunto do certificado selecionando **assunto** e o nome da entidade atribuída e as propriedades associadas serão exibidas.

11. Para exibir os nomes alternativos da entidade atribuída, selecione **nome alternativo do assunto**. Todos os nomes alternativos de assunto atribuídos são exibidos aqui. Os nomes alternativos de entidades encontrados aqui são do tipo **DNS Name** por padrão. Você deve ver os membros a seguir (todos eles devem ter nomes de domínio totalmente qualificados, conforme representado nos registros do host DNS (A ou, se IPv6 AAAA):
    
      - Nome do pool para este pool ou o nome do servidor único se não for um pool
    
      - Nome do servidor ao qual o certificado está atribuído
    
      - Registros de URL simples, geralmente se encontram e se interligarem
    
      - Serviços Web internos e serviços Web nomes externos (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas opções feitas no construtor de topologias e nas seleções de serviços Web do ridden.
    
      - Se já foi atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<registros\> sipdomain.
    
    O último item é o que você está mais interessado – se houver uma entrada de SAN lyncdiscover e lyncdiscoverinternal.
    
    Repita essas etapas se você tiver vários certificados para verificar. Depois que tiver essas informações, você poderá fechar o modo de exibição de certificado e o MMC.

12. Se um nome alternativo de requerente do serviço de descoberta automática estiver ausente, e você estiver usando um único certificado padrão para os tipos padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver muitos domínios SIP, não poderá usar o novo parâmetro AllSipDomain. Em vez disso, você precisa usar o parâmetro DomainName. Ao usar o parâmetro DomainName, você precisa definir o FQDN dos registros lyncdiscoverinternal e lyncdiscover. Por exemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para atribuir o certificado, digite o seguinte:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Onde "impressão digital" é a impressão digital exibida para o certificado recém emitido.

13. Para obter uma SAN de descoberta automática interna ausente ao usar certificados separados para padrão, WebServicesInternal e WebServicesExternal, faça o seguinte:
    
      - No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver muitos domínios SIP, não poderá usar o novo parâmetro AllSipDomain. Em vez disso, você precisa usar o parâmetro DomainName. Ao usar o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para obter um nome alternativo de assunto de descoberta automática externo ausente, na linha de comando, digite:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Se você tiver muitos domínios SIP, não poderá usar o novo parâmetro AllSipDomain. Em vez disso, você precisa usar o parâmetro DomainName. Ao usar o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP. Por exemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para atribuir os tipos de certificados individuais, digite o seguinte:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Em que "impressão digital" é a impressão digital exibida para os certificados individuais emitidos recentemente.
    
    <div>
    

    > [!NOTE]  
    > Só para observar, as etapas 12 e 13 devem ser executadas somente se a conta que a executa tiver acesso à autoridade de certificação com as permissões apropriadas. Se não for possível fazer logon com uma conta que tenha essas permissões ou se você estiver usando uma autoridade de certificação pública ou remota para seus certificados, você precisará solicitá-las por meio do assistente de implantação do Lync Server, que foi tocado na parte superior da correspondente.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

