---
title: 'Lync Server 2013: implantar a ferramenta SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91392470d47cc4d59130e7c304656f9eee48ae5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531368"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Implantar a ferramenta SEFAUtil no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a ferramenta SEFAUtil Resource Kit. A ferramenta faz parte das ferramentas do Lync Server 2013 Resource Kit. Antes de instalar o SEFAUtil, você deve ter um pool de aplicativos confiáveis em sua topologia, especificar SEFAUtil como um aplicativo confiável e habilitar a topologia.

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK deve ser instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil.



</div>

Você pode executar o SEFAUtil em qualquer pool de front-ends em sua implantação.

<div>


> [!NOTE]  
> Para obter mais detalhes sobre a execução do SEFAUtil, consulte o artigo do blog da TechNet, "How to Get SEFAutil Running?" em <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .



</div>

<div>

## <a name="to-deploy-sefautil"></a>Para implantar o SEFAUtil

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. Se necessário, defina um pool de aplicativos confiáveis para o pool de front-ends onde você planeja executar o SEFAUtil. Na linha de comando, execute:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Você pode usar uma porta diferente, se necessário.

    
    </div>

5.  Habilite a topologia com suas alterações. Na linha de comando, execute:
    
        Enable-CsTopology

6.  Instale as ferramentas do kit de recursos do Lync Server 2013 em um servidor front-end que esteja no pool de aplicativos confiáveis que você criou na etapa 3.

7.  Verifique se a ferramenta SEFAUtil está funcionando corretamente, da seguinte maneira:
    
    1.  Execute a ferramenta a partir do prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário em sua implantação.
        
        <div>
        

        > [!NOTE]  
        > A ferramenta está localizada em \Program Files\Microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Exibir as configurações de encaminhamento de chamadas de um usuário. Na linha de comando, execute:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        As configurações de encaminhamento de chamadas para o usuário serão exibidas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

