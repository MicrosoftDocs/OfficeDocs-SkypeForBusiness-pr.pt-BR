---
title: 'Lync Server 2013: entrar e usar o Lync 2013 na máquina virtual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e530f24150bac692717cefb2412712bf3bf8dd1c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Entrar e usar o Lync 2013 na máquina virtual

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Depois que o plug-in VDI estiver habilitado, as seguintes etapas ocorrerão quando o usuário entrar no Lync 2013.

1.  O usuário digita suas credenciais no cliente do Lync 2013 em execução na máquina virtual.

2.  Depois que o Lync detectar a disponibilidade do plug-in VDI, o Lync solicitará que o usuário insira novamente suas credenciais. Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.

3.  O Lync começa a emparelhar com o plug-in VDI. Antes que o emparelhamento seja concluído, o cliente exibe dois ícones na barra de status do Lync. O ícone no canto inferior esquerdo indica que nenhum dispositivo de áudio está disponível, e o ícone piscante no canto inferior direito indica que o emparelhamento de VDI está em andamento:
    
    ![Ícone do Lync VDI mostrando emparelhamento bem-sucedido](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Ícone do Lync VDI mostrando emparelhamento bem-sucedido")  

4.  Após o emparelhamento bem-sucedido de VDI, os ícones mudarão para indicar o dispositivo de áudio que será usado para chamadas e o êxito do emparelhamento de VDI:
    
    ![Ícone de emparelhamento de VDI do Lync mostrando êxito](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Ícone de emparelhamento de VDI do Lync mostrando êxito")  

5.  Após os pares do Lync com o plug-in VDI, o usuário pode ver sua presença em dispositivos compatíveis com Lync conectados ao computador local. Agora, o usuário poderá realizar e atender chamadas como de costume.

</div>

<span> </span>

</div>

</div>

</div>

