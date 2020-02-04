---
title: 'Lync Server 2013: Testar a implantação de pool'
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
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Testar a implantação de pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-09-25_

O procedimento a seguir descreve como testar a implantação do pool de front-end.

<div>

## <a name="to-test-the-pool-deployment"></a>Para testar a implantação do pool

1.  Use computadores e usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função Administrador para a implantação do Lync Server 2013 (em que o painel de controle do Lync Server 2013 está instalado) no grupo **CSAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Lync Server, que afirma que "não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)."

    
    </div>

2.  Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.
    
    <div>
    

    > [!NOTE]  
    > A conta de usuário não pode ser o administrador local de qualquer servidor que esteja executando o Lync Server 2013.

    
    </div>

3.  Use a conta administrativa para fazer logon no computador em que o painel de controle do Lync Server está instalado.

4.  Inicie o painel de controle do Lync Server e forneça as credenciais, se for solicitado. O painel de controle do Lync Server exibe informações de implantação.

5.  Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e se uma marca de seleção verde para o status de replicação está ao lado de cada função de servidor do Lync que foi implantada e colocada online.

6.  Na barra de navegação esquerda, clique em **Usuários** e em **Habilitar usuários**.

7.  Na página **novo usuário do Lync Server** , clique em **Adicionar**.

8.  Para definir os parâmetros de pesquisa para os objetos que deseja localizar, na página **Selecionar do Active Directory**, você pode selecionar **Pesquisa** e, opcionalmente, clique em **Adicionar filtro**. Também é possível selecionar **Pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Depois de decidir nas opções de pesquisa, **Localize**o o.

9.  No painel resultados da pesquisa, selecione todos os objetos para esta sessão de pesquisa e clique em **OK**.

10. Na página **novo usuário do Lync Server** , o objeto ou os objetos selecionados estão na exibição **usuários** . Na lista **atribuir usuários a um pool** , selecione o servidor em que os objetos devem ser hospedados.
    
    Veja a seguir várias opções para configurar os objetos.
    
      - **Gerar o URI SIP do usuário**
    
      - **Telefonia**
    
      - **URI de linha**
    
      - **Política de conferência**
    
      - **Política de versão do cliente**
    
      - **Política de PIN**
    
      - **Política de acesso externo**
    
      - **Política de arquivamento**
    
      - **Política local**
    
      - **Política de cliente**
    
    Para fins de teste da funcionalidade básica, selecione a opção que você prefere para a configuração **gerar URI SIP do usuário** (as outras opções na configuração usarão as configurações padrão) e clique em **habilitar**.

11. Será exibida uma página de resumo que mostra uma marca de seleção na coluna **habilitado** para indicar que os objetos estão agora prontos para uso. A coluna **Endereço SIP** exibe o endereço necessário para a configuração de login do usuário.

12. Registrar um usuário em um computador que ingressou no domínio e outro usuário em outro computador no domínio.

13. Instale o Lync 2013 em cada um dos dois computadores cliente e verifique se os dois usuários podem entrar no Lync Server 2013 e enviar mensagens de chat para os outros.

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

