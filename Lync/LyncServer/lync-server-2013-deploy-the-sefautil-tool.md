---
title: 'Lync Server 2013: implantar a ferramenta SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0783ab251359582d232d558da2161a149dea5117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a ferramenta kit de recursos do SEFAUtil. A ferramenta faz parte das ferramentas do Lync Server 2013 Resource Kit. Antes de poder instalar o SEFAUtil, você deve ter um pool de aplicativos confiável na sua topologia, especificar SEFAUtil como um aplicativo confiável e habilitar a topologia.

<div>


> [!IMPORTANT]  
> O Microsoft UCMA (Unified Communications Managed API) 3.0 Core SDK deve estar instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil.



</div>

Você pode executar o SEFAUtil em qualquer pool de front-ends na sua implantação.

<div>


> [!NOTE]  
> Para obter mais detalhes sobre como executar o SEFAUtil, consulte o artigo do blog do TechNet "como fazer SEFAutil executar?" em <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.



</div>

<div>

## <a name="to-deploy-sefautil"></a>Para implantar a SEFAUtil

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  A ferramenta SEFAUtil só pode ser executada em um computador que integra um pool de aplicativos confiáveis. Se necessário, defina um pool de aplicativos confiável para o pool de front-ends em que você planeja executar o SEFAUtil. Na linha de comando, execute:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Se necessário, você pode usar uma porta diferente.

    
    </div>

5.  Habilite a topologia com suas alterações. Na linha de comando, digite:
    
        Enable-CsTopology

6.  Instale as ferramentas do Lync Server 2013 Resource Kit em um servidor front-end que está no pool de aplicativos confiáveis que você criou na etapa 3.

7.  Verifique se a ferramenta SEFAUtil está sendo executada corretamente conforme segue:
    
    1.  Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário de sua implantação.
        
        <div>
        

        > [!NOTE]  
        > A ferramenta está localizada em \Arquivos de Programas\microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Exiba as configurações de encaminhamento de chamada de um usuário, Na linha de comando, execute:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        As configurações de encaminhamento de chamada do usuário serão exibidas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

