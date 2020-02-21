---
title: 'Lync Server 2013: editar o diagrama de configuração de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225702f30aa19bf53c8b3f65c9731ea29b16a686
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Editando o diagrama de configuração de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

A maior parte do trabalho que um designer faz no Lync Server 2013, a ferramenta de planejamento consiste em definir as entradas para os endereços IP e FQDNs (nomes de domínio totalmente qualificados) para as entradas no diagrama de rede. As informações inseridas nesta página são transferidas para os relatórios e outras informações contidas na ferramenta de planejamento.

![Diagrama de rede da ferramenta de planejamento](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagrama de rede da ferramenta de planejamento")

A ferramenta de planejamento cria um diagrama de rede com texto padrão para endereços IP e FQDNs.

Para editar os valores de entrada e diagrama de rede:

1.  Escolha uma seção da rede para começar a trabalhar. Por exemplo, clique duas vezes no texto **Access1.contoso.com**. Na caixa de diálogo que é aberta, digite o FQDN real do servidor access1.contoso.com e o endereço IP real, substituindo o 131.107.155.3.

2.  Clique em **OK** para salvar as entradas.

3.  Continue a editar os endereços IP e os FQDNs, fornecendo endereços IP virtuais para balanceadores de carga de hardware ou entradas de servidor para balanceamento de carga do DNS (Sistema de Nome de Domínio) para servidores em pools.

Um recurso útil da Ferramenta de Planejamento é que ela pode atribuir incrementalmente um intervalo de endereços IP e nomes de host do servidor, em vez de exigir que o designer edite cada servidor separado em um pool. Por exemplo:

1.  Clique duas vezes nos Servidores Front-End em pool. Quando a caixa de diálogo abrir, selecione **Deseja usar os IPs e o FQDN como pontos de partida para todos os servidores equivalentes neste cluster?**.

2.  Por exemplo, o valor inicial para o primeiro servidor é fe0101.contoso.com e um endereço IP de 192.168.21.122.

3.  Digite **FE0.contoso.com** em **FQDN do servidor front-end**, digite **192.168.21.131** no **endereço IP do servidor front-end**e clique em **OK**.

4.  O recurso de incremento automático atualiza todos os servidores no pool para fe01 até fe06 e todos os endereços IP de 192.168.21.131 para 136.

Depois de concluir todas as edições, salve a topologia executando as seguintes etapas:

Para salvar o design da ferramenta de planejamento, clique em **arquivo**e, em seguida, clique em **salvar topologia** ou **salvar topologia como**. Se uma caixa de diálogo **Salvar Ferramenta de Planejamento como** for exibida, digite um nome para o arquivo em **Nome do arquivo** e clique em **Salvar**.

<div>

## <a name="see-also"></a>Confira também


[Editando o design no Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

