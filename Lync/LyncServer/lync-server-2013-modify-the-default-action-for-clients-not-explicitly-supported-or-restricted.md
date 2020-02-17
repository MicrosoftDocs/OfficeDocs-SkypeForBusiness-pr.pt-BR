---
title: Modificar a ação padrão para clientes não explicitamente suportados ou restritos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ff08d05c9c8c18b7f81f22b04e2168a14f1a8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modificar a ação padrão para clientes não explicitamente suportados ou restritos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Além de especificar a versão de clientes que você deseja suportar no seu ambiente do Lync Server 2013, você também pode especificar uma ação padrão para clientes que ainda não têm uma política de versão definida. Isso permite que você restrinja quais versões do cliente são usadas no seu ambiente do Lync Server, o que pode ajudá-lo a controlar os custos associados ao suporte a várias versões de cliente.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Para modificar a ação padrão para clientes não explicitamente suportados ou restritos

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e em **Configuração de Versão de Cliente**.

4.  Na página **Configuração de Versão de Cliente**, clique duas vezes na configuração **Global** da lista.

5.  Na caixa de diálogo **Editar Configuração de Versão de Cliente**, verifique se que a caixa de seleção **Habilitar Controle de Versão** está marcada e, em **Ação padrão**, selecione uma das seguintes opções:
    
      - **Permitir**   permite que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** .
    
      - **Bloquear**   impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** .
    
      - **Bloquear com URL**   impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** e incluir uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.
    
      - **Permitir com URL**   permite que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** e incluir uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.

6.  Se você tiver selecionado **Bloquear com URL**, digite a URL de download do cliente para incluir na mensagem de erro na caixa **URL**.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Para desabilitar o controle de versão de cliente

  - Para desabilitar o controle de versão para permitir que todos os clientes façam logon, independentemente da versão de cliente, desmarque a caixa de seleção **Habilitar controle de versão** e clique em **Confirmar**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modificar a ação padrão usando cmdlets do Windows PowerShell

A ação padrão a ser tomada quando os usuários tentam fazer logon usando clientes que não são explicitamente suportados ou restritos por uma política de versão do cliente podem ser gerenciados usando a interface de linha de comando do Windows PowerShell e o cmdlet **set-CsClientVersionPolicy** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Para configurar a ação padrão para bloquear o acesso

  - O seguinte comando define a ação padrão para o bloqueio do site de Redmond. Isso bloqueará o registro de qualquer cliente para o qual nenhuma regra de configuração de versão do cliente existir.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Para configurar a ação padrão para permitir o acesso

  - Neste exemplo, a ação padrão para o site de Redmond é definir como Permitir. Isso permitirá o registro de qualquer cliente para o qual nenhuma regra de configuração de versão do cliente existir.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Confira Também


[Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

