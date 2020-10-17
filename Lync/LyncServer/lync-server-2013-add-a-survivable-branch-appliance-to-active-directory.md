---
title: 'Lync Server 2013: adicionar um aparelho de filial persistente ao Active Directory'
description: 'Lync Server 2013: adicionar um aparelho de filial persistente ao Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd06332679be0819cf3002f344a62a7ce1d5a9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567887"
---
# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Adicionar um aparelho de filial persistente ao Active Directory no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-23_

Se você planeja implantar um aparelho de filial persistente, você deve adicionar o aparelho de filial persistente aos serviços de domínio do Active Directory. Execute este procedimento no local central.

<div>


> [!IMPORTANT]  
> Execute este procedimento somente se você estiver implantando um aparelho de filial persistente. Não o execute se você estiver implantando um servidor de filial persistente.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Para adicionar um Aparelho de Filial Persistente aos Serviços de Domínio do Active Directory

1.  Faça logon em um servidor membro como um membro do grupo Administração de Empresa.

2.  Clique em **Iniciar**, depois em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.

3.  No menu **Ações**, clique em **Novo** e, em seguida, clique em **Computador**.

4.  Na caixa de diálogo **novo objeto-computador** , digite um nome para o objeto do computador do aparelho de filial persistente (por exemplo, BranchOffice1) e clique em **alterar**.

5.  Na caixa de diálogo **Selecionar Usuário ou Grupo**, adicione o grupo RTCUniversalSBATechnicians e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Um membro do grupo RTCUniversalSBATechnicians no site da filial adicionará esse dispositivo ao domínio posteriormente.

    
    </div>

6.  Clique em **OK** para salvar o objeto computador de aparelho de filial persistente.

7.  Clique em **Iniciar**, em **Ferramentas Administrativas** e em **Editor ADSI**.

8.  No **Editor ADSI**, clique com o botão direito do mouse no objeto de computador que você criou nas etapas anteriores e clique em **Propriedades**.

9.  Na lista de atributos, clique em **servicePrincipalName** e em **Editar**.

10. No campo **valor a ser adicionado** , digite host/ \<SBA FQDN\> onde \<SBA FQDN\> é o nome de domínio totalmente qualificado (FQDN) do seu aparelho de filial persistente. Por exemplo, digite **HOST/BranchOffice1.contoso.com**.

11. Clique em **OK** para  salvar a configuração do atributo **servicePrincipalName** e, em seguida, clique em **OK** para salvar as propriedades do objeto de computador.

12. Em **Usuários e Computadores do Active Directory**, clique com o botão direito do mouse em **Usuários**, clique em **Novo** e em **Usuário**.

13. Insira informações no Assistente para criar uma conta de usuário de domínio para um técnico de aparelho de filial persistente.

14. Em **Usuários e Computadores do Active Directory**, clique em **Usuários**, clique com o botão direito do mouse no objeto de usuário e clique em **Adicionar a um grupo**.

15. Em **Digite os nomes de objetos a serem selecionados**, digite **RTCUniversalSBATechnicians** e clique em **OK**.

16. Repita as etapas 12 a 15 para cada técnico do site de filial.

**Próxima etapa**: [adicionar sites de filiais à sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

