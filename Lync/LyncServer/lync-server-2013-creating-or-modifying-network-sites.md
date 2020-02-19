---
title: 'Lync Server 2013: Criando ou modificando sites de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67d4fedf5931a85772e42a87fb80c382a364ae96
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Criando ou modificando sites de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-08_

Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado. Você pode usar o painel de controle do Microsoft Lync Server 2013 para configurar sites e associá-los a regiões. Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver. Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda. No painel de controle do Lync Server, você pode criar, modificar e excluir sites de rede. Use os procedimentos a seguir para criar ou modificar um site da rede. Para obter detalhes sobre como excluir um site de rede existente, consulte [excluindo um site de rede existente no Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Para criar um local de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.

4.  Na página **Local**, clique em **Novo**.

5.  Em **Novo Local**, digite um nome para este local no campo **Nome**.
    
    <div>
    

    > [!NOTE]  
    > Os nomes de site devem ser exclusivos na implantação do Lync Server 2013.

    
    </div>

6.  Na lista suspensa **Região**, selecione uma região da rede para associar a este local.

7.  (Opcional) Se deseja impor limitações de largura de banda em chamadas de áudio ou vídeo para este local, selecione o perfil da política da largura de banda com as configurações apropriadas na lista suspensa **Política da largura de banda**.
    
    <div>
    

    > [!NOTE]  
    > Você pode ver os detalhes dos perfis disponíveis da política de largura de banda, ou criar um novo perfil, na página <STRONG>Perfil de Política</STRONG> do grupo <STRONG>Configuração de Rede</STRONG>. Para obter detalhes, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">criando ou modificando perfis de política de largura de banda no Lync Server 2013</A>.

    
    </div>

8.  (Opcional) Se deseja fornecer configurações de localização para esse local, selecione uma política de localização na lista suspensa **Política de localização**.
    
    <div>
    

    > [!NOTE]  
    > A política de localização atribui configurações específicas de 9-1-1 Aprimorado (E9-1-1) e de localização do cliente ao local. Você pode ver os detalhes das políticas de localização disponíveis ou criar uma política nova na página <STRONG>Política de localização</STRONG> do grupo <STRONG>Configuração de Rede</STRONG>. Para obter detalhes, consulte <A href="lync-server-2013-viewing-location-policy-information.md">Viewing Location Policy Information in Lync Server 2013</A>.

    
    </div>

9.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse local, que não podem ser expressadas apenas pelo nome.

10. Clique em **Comprometer**.
    
    <div>
    

    > [!NOTE]  
    > Você não usa a tabela <STRONG>Sub-redes Associadas</STRONG> ao criar um novo local de rede. Você associa a sub-rede ao local quando criá-la ou modificá-la. Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">create or Modify Network sub-redes in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Para modificar um local de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.

4.  Na página **Local**, clique no local que deseja modificar.

5.  No painel **Ações**, clique em **Mostrar detalhes**.

6.  Na página **Editar Local**, você pode modificar a descrição, região, perfil da política da largura de banda e política de localização associados ao novo local. Para obter os detalhes, consulte a seção "Para criar um local de rede" anteriormente neste tópico.

7.  Clique em **Comprometer**.

Você não pode modificar a tabela **Sub-redes Associadas** nesta página. A lista de sub-redes associadas é fornecida para referência, para que você saiba quais sub-redes serão afetadas quando você modificar as configurações do local.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Para excluir um local de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.

4.  Na página **Local**, clique no local que deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um local de cada vez. Para fazer isso, pressione CTRL e selecione diversos locais mantendo a tecla pressionada. Ou então, para selecionar todos os locais, clique em <STRONG>Selecionar Tudo</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Você não poderá remover um local de rede se ele estiver associado a uma sub-rede. Se você tentar fazer isso, receberá uma mensagem de erro. Para ver se o local está associado a alguma sub-rede, clique no local e em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo um site de rede existente no Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

