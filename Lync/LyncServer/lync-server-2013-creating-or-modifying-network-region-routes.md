---
title: 'Lync Server 2013: Criando ou modificando rotas de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Criando ou modificando rotas de região de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-08_

Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões. Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra. Você pode usar o painel de controle do Lync Server para configurar rotas de região de rede. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para criar ou modificar uma rota de região de rede. Para obter detalhes sobre como excluir um roteiro de região de rede existente, consulte [excluindo rotas de região de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Para criar uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **rota de região**.

4.  Na página **rota de região** , clique em **novo**.

5.  Em **nova rota de região**, digite um valor no campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > Esse valor deve ser exclusivo na implantação do Microsoft Lync Server 2013.

    
    </div>

6.  Na lista suspensa **região \#de rede 1** , selecione uma das duas regiões a serem conectadas por essa rota.

7.  Na lista suspensa **região \#de rede 2** , selecione a outra região para esta rota. Esta região deve ser diferente da região selecionada para a região \#de rede 1.

8.  Use a caixa de listagem de **links de região de rede** para adicionar links de região ao roteiro. Clique no botão **Adicionar** para exibir a página de **link de região** . Clique em um link de região para adicionar a essa rota e, em seguida, clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Continue a clicar no botão <STRONG>Adicionar</STRONG> para adicionar mais links ou selecionar um link e clicar em <STRONG>remover</STRONG> para remover um link.

    
    </div>

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Para modificar uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **rota de região**.

4.  Na página **rota de região** , clique na rota de região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar rota de região**, você pode modificar as regiões Unidas por essa rota e os links de região associados à rota.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo rotas de região de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

