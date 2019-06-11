---
title: 'Lync Server 2013: Criando ou modificando sites de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Criando ou modificando sites de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-08_

Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada. Você pode usar o painel de controle do Microsoft Lync Server 2013 para configurar sites e associá-los a regiões. Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver. Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda. No painel de controle do Lync Server, você pode criar, modificar e excluir sites de rede. Use os procedimentos a seguir para criar ou modificar um site de rede. Para obter detalhes sobre como excluir um site de rede existente, consulte [excluindo um site de rede existente no Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Para criar um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **site**.

4.  Na página do **site** , clique em **novo**.

5.  Em **novo site**, digite um nome para este site no campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > Os nomes dos sites devem ser exclusivos na implantação do Lync Server 2013.

    
    </div>

6.  Na lista suspensa **região** , selecione uma região de rede para associar a este site.

7.  Adicionais Se você quiser colocar as limitações de largura de banda em chamadas de áudio ou vídeo para este site, selecione o perfil da política de largura de banda com as configurações apropriadas na lista suspensa **política de largura de banda** .
    
    <div>
    

    > [!NOTE]  
    > Você pode exibir os detalhes dos perfis da política de largura de banda disponíveis ou criar um novo perfil de política de largura de banda na página <STRONG>perfil da política</STRONG> do grupo <STRONG>configuração de rede</STRONG> . Para obter detalhes, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">criando ou modificando perfis de política de largura de banda no Lync Server 2013</A>.

    
    </div>

8.  Adicionais Se você quiser fornecer configurações de localização para este site, selecione uma política de localização na lista suspensa **política de localização** .
    
    <div>
    

    > [!NOTE]  
    > A política de localização atribui configurações de localização avançada de 9-1-1 (E9-1-1) e de cliente de cliente (-1-1) específicas ao site. Você pode exibir os detalhes das políticas de localização disponíveis ou criar uma nova política de localização, na página <STRONG>política de localização</STRONG> do grupo de <STRONG>configuração de rede</STRONG> . Para obter detalhes, consulte <A href="lync-server-2013-viewing-location-policy-information.md">exibindo informações de política de localização no Lync Server 2013</A>.

    
    </div>

9.  Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse site que não pode ser expresso apenas pelo nome.

10. Clique em **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > Você não usa a tabela de <STRONG>sub-redes associadas</STRONG> quando cria um novo site de rede. Você associa uma sub-rede a um site quando cria ou modifica a sub-rede. Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">criar ou modificar sub-redes de rede no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Para modificar um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **site**.

4.  Na página do **site** , clique no site que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar site** , você pode modificar a descrição, a região, o perfil da política de largura de banda e a política de localização associada ao site. Para obter detalhes, consulte a seção "para criar um site de rede" anteriormente neste tópico.

7.  Clique em **Confirmar**.

Não é possível modificar a tabela de **sub-redes associadas** nesta página. A lista de sub-redes associadas é fornecida para referência para que você saiba quais são as sub-redes que serão afetadas quando você modificar as configurações do site.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Para excluir um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **site**.

4.  Na página do **site** , clique no site que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um site de cada vez. Para fazer isso, pressione CTRL e selecione vários sites enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todos os sites, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Você não pode remover um site de rede se ele estiver associado a uma sub-rede de rede. Se você tentar remover um site associado a uma sub-rede, receberá uma mensagem de erro. Para ver se um site está associado a qualquer sub-rede, clique no site e, em seguida, clique em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG> .

    
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

