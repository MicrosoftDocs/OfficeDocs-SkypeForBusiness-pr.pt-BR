---
title: 'Lync Server 2013: Adicionar um Aplicativo de Filial Persistente ao Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Adicionar um Aplicativo de Filial Persistente ao Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-23_

Se você planeja implantar um aparelho de ramificação sobreviventes, será necessário adicionar o aparelho de ramificação sobreviventes aos serviços de domínio Active Directory. Execute este procedimento no site central.

<div>


> [!IMPORTANT]  
> Execute este procedimento apenas se você estiver implantando um aparelho de ramificação sobreviventes. Não o execute se você estiver implantando um servidor de ramificação sobreviventes.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Para adicionar um aparelho de ramificação sobreviventes aos serviços de domínio do Active Directory

1.  Faça logon em um servidor membro como membro do grupo Administradores da empresa.

2.  Clique em **Iniciar**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.

3.  No menu **ações** , clique em **novo** e, em seguida, clique em **computador**.

4.  Na caixa de diálogo **novo objeto-computador** , digite um nome para o objeto de computador de aparelho de ramificação sobreviventes (por exemplo, BranchOffice1) e, em seguida, clique em **alterar**.

5.  Na caixa de diálogo **Selecionar usuário ou grupo** , adicione o grupo RTCUniversalSBATechnicians e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Um membro do grupo RTCUniversalSBATechnicians no site da filial adicionará esse dispositivo ao domínio mais tarde.

    
    </div>

6.  Clique em **OK** para salvar o objeto de computador de aparelho de ramificação sobreviventes.

7.  Clique em **Iniciar**, em **Ferramentas administrativas**e em **ADSI Editar**.

8.  Em **ADSI Edit**, clique com o botão direito do mouse no objeto de computador que você criou nas etapas anteriores e, em seguida, clique em **Propriedades**.

9.  Na lista atributo, clique em **** servicePrincipalName e, em seguida, clique em **Editar**.

10. No campo **valor para adicionar** \<, digite host/SBA FQDN\> em que \<SBA FQDN\> é o nome de domínio totalmente qualificado (FQDN) do seu aparelho de ramificação sobreviventes. Por exemplo, digite **host/BranchOffice1. contoso. com**.

11. Clique em **OK** para salvar a configuração do atributo **servicePrincipalName** e, em seguida, clique em **OK** para salvar as propriedades do objeto do computador.

12. Em **usuários e computadores do Active Directory**, clique com o botão direito do mouse em **usuários**, clique em **novo**e, em seguida, clique em **usuário**.

13. Insira informações no Assistente para criar uma conta de usuário de domínio para um técnico de appliance de ramificação sobreviventes.

14. Em **usuários e computadores do Active Directory**, clique em **usuários**, clique com o botão direito do mouse no objeto do usuário e, em seguida, clique em **Adicionar a um grupo**.

15. Em **digite os nomes dos objetos a serem selecionados**, digite **RTCUniversalSBATechnicians**e clique em **OK**.

16. Repita as etapas 12-15 para cada técnico de site de filial.

**Próxima etapa**: [adicionar sites de filiais à sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

