---
title: 'Lync Server 2013: testar a implantação do pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46f656453b6ad6eee3eaf8fc0bbc8c26f308fe35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42019012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Testar a implantação do pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-25_

O procedimento a seguir descreve como testar a implantação do pool de front-ends.

<div>

## <a name="to-test-the-pool-deployment"></a>Para testar a implantação do pool

1.  Use usuários e computadores do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para a implantação do Lync Server 2013 (em que o painel de controle do Lync Server 2013 está instalado) no grupo **CSAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Lync Server, que afirma que "não autorizado: acesso negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)."

    
    </div>

2.  Se o objeto de usuário estiver conectado no momento, saia e faça logon novamente para registrar a nova atribuição de grupo.
    
    <div>
    

    > [!NOTE]  
    > A conta de usuário não pode ser o administrador local de qualquer servidor executando o Lync Server 2013.

    
    </div>

3.  Use a conta administrativa para fazer logon no computador onde o painel de controle do Lync Server está instalado.

4.  Inicie o painel de controle do Lync Server e forneça as credenciais, se solicitado. O painel de controle do Lync Server exibe informações de implantação.

5.  Na barra de navegação esquerda, clique em **topologia**e confirme que o status do serviço mostra um computador com uma seta verde e que uma marca de seleção verde para status de replicação é próxima a cada função de servidor do Lync Server que foi implantada e colocada online.

6.  Na barra de navegação esquerda, clique em **usuários**e em **habilitar usuários**.

7.  Na página **novo usuário do Lync Server** , clique em **Adicionar**.

8.  Para definir parâmetros de pesquisa para os objetos que você deseja localizar, na página **selecionar a partir do Active Directory** , você pode selecionar **pesquisa**e, opcionalmente, clicar em **Adicionar filtro**. Você também pode selecionar a **pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Depois de decidir sobre suas opções de pesquisa, **encontre Find**.

9.  No painel de resultados da pesquisa, selecione todos os objetos para esta sessão de pesquisa e clique em **OK**.

10. Na página **novo usuário do Lync Server** , o objeto ou objetos que você selecionou estão na exibição **dos usuários** . Na lista **atribuir usuários a um pool** , selecione o servidor no qual os objetos devem estar hospedados.
    
    A seguir, há várias opções para configurar os objetos.
    
      - **Gerar URI SIP do usuário**
    
      - **Telefonia**
    
      - **URI da linha**
    
      - **Política de conferência**
    
      - **Política de versão do cliente**
    
      - **Política de PIN**
    
      - **Política de acesso externo**
    
      - **Política de arquivamento**
    
      - **Política de local**
    
      - **Política de cliente**
    
    Para fins de teste da funcionalidade básica, selecione a opção que você preferir para a configuração **gerar URI do SIP do usuário** (as outras opções na configuração usarão as configurações padrão) e clique em **habilitar**.

11. É exibida uma página de resumo que mostra uma marca de seleção na coluna **habilitado** para indicar que os objetos agora estão prontos para uso. A coluna **endereço SIP** exibe o endereço que você precisa para a configuração de entrada do usuário.

12. Faça o logon de um usuário em um computador que tenha ingressado no domínio e outro usuário em outro computador no domínio.

13. Instale o Lync 2013 em cada um dos dois computadores cliente e verifique se ambos os usuários podem entrar no Lync Server 2013 e enviar mensagens instantâneas entre si.

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

