---
title: 'Lync Server 2013: criar links de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e8c3d0fd254ba780b91d554402ca38d30f7073
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515558"
---
# <a name="create-network-region-links-in-lync-server-2013"></a>Criar links de região de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Regiões dentro de uma rede são vinculadas através de uma conectividade WAN física. Um *link de região de rede* cria um link entre duas regiões configuradas para controle de admissão de chamada (CAC) e define os limites da largura de banda em tráfego de áudio e vídeo entre estas regiões.

Para obter detalhes sobre como trabalhar com links de região de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

A topologia de exemplo possui um link entre as regiões da América do Norte e APAC e um link entre as regiões EMEA e APAC. Cada um desses links de região é restrito pela largura de banda de WAN, conforme descrito na tabela informações de largura de banda de link de região no [exemplo: reunir seus requisitos para controle de admissão de chamadas na seção do Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) da documentação de planejamento.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Para criar links de região de rede usando o Shell de Gerenciamento do Lync Server

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsNetworkRegionLink para criar os links de região e aplicar os perfis da política de largura de banda adequados. Por exemplo, execute:
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Para criar links de região de rede usando o Painel de controle do Lync Server

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique no botão de navegação **Link de região**.

4.  Clique em **Novo**.

5.  Na página **Novo link de região**, clique em **Nome** e digite um nome para o link de região de rede.

6.  Clique em **região de rede \# 1**e clique na região de rede na lista que você deseja vincular à região de rede \# 2.

7.  Clique em **região de rede \# 2**e, em seguida, clique em uma região de rede na lista que você deseja vincular à região de rede \# 1.

8.  Opcionalmente, clique em **Política da largura de banda** e selecione o perfil da política de largura de banda que deseja aplicar para o link de região de rede.
    
    <div class=" ">
    

    > [!NOTE]  
    > Aplique uma política de largura de banda apenas se o link de região de rede é restrito por largura de banda e se deseja usar o CAC para controlar o tráfego de mídia naquele link.

    
    </div>

9.  Clique em **Confirmar**.

10. Para finalizar a criação de links de região de rede para sua topologia, repita as etapas 4 a 9 com as configurações de outras regiões.

</div>

</div>

<span> </span>

</div>

</div>

</div>
