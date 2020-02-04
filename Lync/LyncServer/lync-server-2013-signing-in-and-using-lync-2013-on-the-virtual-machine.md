---
title: 'Lync Server 2013: Entrando e usando o Lync 2013 na máquina virtual'
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
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Entrando e usando o Lync 2013 na máquina virtual

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Depois que o plug-in VDI estiver habilitado, as seguintes etapas ocorrerão quando o usuário entrar no Lync 2013.

1.  O usuário digita suas credenciais no cliente do Lync 2013 em execução na máquina virtual.

2.  Depois que o Lync detecta a disponibilidade do plug-in VDI, o Lync solicita que o usuário digite novamente suas credenciais. Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.

3.  O Lync começa a emparelhar com o plug-in VDI. Antes da conclusão do emparelhamento, o cliente exibe dois ícones na barra de status do Lync. O ícone no canto inferior esquerdo indica que não há dispositivos de áudio disponíveis, e o ícone piscante no canto inferior direito indica que o emparelhamento VDI está em andamento, conforme mostrado:
    
    ![Ícone de VDI do Lync mostrando o emparelhamento com êxito](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Ícone de VDI do Lync mostrando o emparelhamento com êxito")  

4.  Após o emparelhamento bem-sucedido de VDI, os ícones mudarão para indicar o dispositivo de áudio que será usado para chamadas e o êxito do emparelhamento de VDI:
    
    ![Ícone de emparelhamento da VDI do Lync mostrando sucesso](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Ícone de emparelhamento da VDI do Lync mostrando sucesso")  

5.  Após os pares do Lync com o plug-in VDI, o usuário pode ver sua presença em dispositivos compatíveis com o Lync conectados ao computador local. Agora o usuário pode fazer e atender chamadas normalmente.

</div>

<span> </span>

</div>

</div>

</div>

