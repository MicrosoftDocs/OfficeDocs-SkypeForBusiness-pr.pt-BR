---
title: 'Lync Server 2013: definir um servidor ou aparelho de filial persistente'
description: 'Lync Server 2013: definir um servidor ou aparelho de filial persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946aec82f33dffe268fefb3548b8db2f5c19e1a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567757"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definir um servidor ou aparelho de filial persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-07_

Execute este procedimento no local central caso não tenha definido o Servidor ou o Aparelho de Filial Persistente quando o adicionou à sua topologia.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Para definir um aparelho de filial persistente ou servidor de filial persistente

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na árvore do console, expanda o site central, expanda **sites de filial**e, em seguida, expanda o nome do site de filial onde você planeja implantar o aparelho de filial persistente ou servidor de filial persistente.

3.  Clique com o botão direito em **aparelhos de filial persistente**e, em seguida, clique em **novo aparelho de filial persistente**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Aparelhos de filial persistentes</STRONG> é onde você define servidores de filial persistente e aparelhos de filial persistente.

    
    </div>

4.  Na caixa de diálogo **definir aparelho de filial persistente** , clique em **FQDN**, digite o FQDN (nome de domínio totalmente qualificado) do aparelho de filial persistente ou servidor de filial persistente que você irá implantar neste site de filial e clique em **Avançar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você estiver definindo um aparelho de filial persistente, o nome inserido no <STRONG>FQDN</STRONG> deve ser o mesmo que o FQDN do aparelho de filial persistente que você atribuiu ao atributo <STRONG>servicePrincipalName</STRONG> . Para obter detalhes, consulte <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Adicionar um aparelho de filial persistente ao Active Directory no Lync Server 2013</A>.

    
    </div>

5.  Clique em **pool de front-ends**, clique no servidor de front-end (pool de serviços de usuário) no site central ao qual esse aparelho de filial persistente ou servidor de filial persistente se conectará e clique em **Avançar**.

6.  Clique em **servidor de borda**, clique no pool de borda que esse aparelho de filial persistente ou servidor de filial persistente se conectará para fornecer conectividade PSTN aos usuários remotos do site de filial e clique em **Avançar**.

7.  Clique em **FQDN de gateway ou endereço IP**e, em seguida, digite o FQDN ou endereço IP do ponto de gateway que o aparelho de filial persistente ou servidor de filial persistente está associado para rotear chamadas PSTN de entrada ou saída.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você está definindo um Aparelho de Filial Persistente, este é o gateway ao qual o Servidor de Mediação dentro do Aparelho de Filial Persistente se conectará para obter conectividade PSTN.

    
    </div>

8.  Clique em **Porta de Escuta para Gateway de IP/PSTN** e aceite a porta padrão.

9.  No **protocolo de transporte SIP**, clique no protocolo de transporte que o aparelho de filial persistente ou servidor de filial persistente usará e clique em **concluir**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, recomendamos que você use o TLS. Caso esteja definindo um Aparelho de Filial Persistente, consulte sua documentação do fornecedor do Aparelho de Filial Persistente para verificar se o seu Aparelho de Filial Persistente é compatível com protocolo TLS.

    
    </div>

10. Na árvore do console, clique com o botão direito no novo Aparelho ou Servidorde Filial Persistente, clique em **Topologia** e em **Publicar**.

**Próxima etapa**: [implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

