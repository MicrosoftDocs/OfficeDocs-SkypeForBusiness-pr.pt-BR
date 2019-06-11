---
title: 'Lync Server 2013: Definir um Servidor ou Aparelho de Filial Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definir um Servidor ou Aparelho de Filial Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-07_

Execute este procedimento no site central se você não definiu o aplicativo ou o aplicativo da ramificação sobreviventes quando o adicionou à sua topologia.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Para definir um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site central, expanda **sites**de ramificação e, em seguida, expanda o nome do site de ramificação no qual você planeja implantar o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.

3.  Clique com o botão direito do mouse em **aparelhos de ramificação sobreviventes**e clique em **novo aplicativo de ramificação sobreviventes**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Aparelhos de ramificação sobreviventes</STRONG> é onde você define servidores de ramificação sobreviventes e aparelhos de ramificação sobreviventes.

    
    </div>

4.  Na caixa de diálogo **definir equipamento de ramificação sobreviventes** , clique em **FQDN**, digite o nome de domínio totalmente qualificado (FQDN) da ferramenta de ramificação sobreviventes ou do servidor de ramificação sobreviventes que você irá implantar nesse site de filial e clique em **Avançar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você estiver definindo um aparelho de ramificação sobreviventes, o nome que você inserir no <STRONG>FQDN</STRONG> deve ser o mesmo que o FQDN do aparelho de ramificação sobreviventes atribuído ao atributo <STRONG>servicePrincipalName</STRONG> . Para obter detalhes, consulte <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Adicionar um aparelho de ramificação sobreviventes ao Active Directory no Lync Server 2013</A>.

    
    </div>

5.  Clique em **pool de front-end**, clique no servidor front-end (pool de serviços do usuário) no site central em que esse aparelho de ramificação de persistência ou o servidor de ramificação sobreviventes se conectará e, em seguida, clique em **Avançar**.

6.  Clique em **servidor de borda**, clique no pool de bordas em que esse aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se conectará para fornecer conectividade PSTN a usuários remotos do site de filial e clique em **Avançar**.

7.  Clique em **endereço IP ou FQDN do gateway**e, em seguida, digite o FQDN ou endereço IP do par de gateways que o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes está associado para chamadas PSTN de entrada ou de saída.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você estiver definindo um aparelho de ramificação sobreviventes, esse é o gateway ao qual o servidor de mediação dentro da ramificação de ramificação sobreviventes se conectará para conectividade PSTN.

    
    </div>

8.  Clique em **porta de escuta do gateway IP/PSTN**e aceite a porta padrão.

9.  Em **protocolo de transporte SIP**, clique no protocolo de transporte o aplicativo de ramificação sobreviventes ou o servidor de ramificação sobreviventes será usado e clique em **concluir**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, recomendamos enfaticamente que você use Transport Layer Security (TLS). Se você estiver definindo um aparelho de ramificação sobreviventes, confira a documentação do fornecedor da sua agência de ramificação sobreviventes para verificar se o seu aparelho de ramificação sobreviventes é compatível com o protocolo TLS.

    
    </div>

10. Na árvore do console, clique com o botão direito do mouse no novo aplicativo ou aplicativo da ramificação sobreviventes, clique em **topologia**e, em seguida, clique em **publicar**.

**Próxima etapa**: [implantar um aplicativo ou um aplicativo de ramificação sobreviventes com o Lync Server 2013-tarefa do site de ramificação](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

