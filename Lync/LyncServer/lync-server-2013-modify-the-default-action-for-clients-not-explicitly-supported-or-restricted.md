---
title: Modificar a ação padrão para clientes sem suporte explícito ou restrito
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modificar a ação padrão para clientes sem suporte explícito ou restrito no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Além de especificar a versão dos clientes para a qual você deseja dar suporte no ambiente do Lync Server 2013, você também pode especificar uma ação padrão para os clientes que ainda não têm uma política de versão definida. Isso permite que você restrinja quais versões do cliente são usadas em seu ambiente do Lync Server, o que pode ajudá-lo a controlar os custos associados ao suporte a várias versões de cliente.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Para modificar a ação padrão para clientes sem suporte explícito ou restrito

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique em **configuração de versão do cliente**.

4.  Na página **configuração de versão do cliente** , clique duas vezes na configuração **global** na lista.

5.  Na caixa de diálogo **Editar configuração da versão do cliente** , verifique se a caixa de seleção **habilitar controle de versão** está marcada e, em seguida, em **ação padrão**, selecione uma das seguintes opções:
    
      - **Permitir**   permite que o cliente faça logon se a versão do cliente não coincidir com nenhum filtro na lista de **políticas de versão do cliente** .
    
      - **Bloquear**   impede que o cliente faça logon se a versão do cliente não coincidir com nenhum filtro na lista de **políticas de versão do cliente** .
    
      - **Bloquear com URL**   impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** e incluir uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.
    
      - **Permitir com URL**   permite que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** e incluir uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.

6.  Se você selecionou **Bloquear com URL**, digite a URL de download do cliente a ser incluída na mensagem de erro na caixa **URL** .

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Para desabilitar o controle de versão do cliente

  - Para desabilitar o controle de versão para permitir que todos os clientes façam logon independentemente da versão do cliente, desmarque a caixa de seleção **habilitar controle de versão** e clique em **confirmar**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modificando a ação padrão usando cmdlets do Windows PowerShell

A ação padrão a ser tomada quando os usuários tentam entrar usando clientes que não têm suporte explícito ou restrições por uma política de versão do cliente podem ser gerenciadas usando a interface de linha de comando do Windows PowerShell e o cmdlet **set-CsClientVersionPolicy** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Para configurar a ação padrão para bloquear o acesso

  - O comando a seguir define a ação padrão para o bloco de site Redmond. Isso bloqueará o registro de qualquer cliente para o qual não existe uma regra de configuração de versão do cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Para configurar a ação padrão para permitir o acesso

  - Neste exemplo, a ação padrão para o site Redmond é definida como permitir. Isso permitirá o registro de qualquer cliente para o qual não existe uma regra de configuração de versão do cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Para obter detalhes, consulte o tópico da ajuda para o cmdlet [set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

