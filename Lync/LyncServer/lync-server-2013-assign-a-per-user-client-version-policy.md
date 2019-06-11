---
title: 'Lync Server 2013: atribuir uma política de versão de cliente por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bfd26aff4ae2e5d8dacf7ec145bec0e3247facf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836753"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Atribuir uma política de versão de cliente por usuário no Lync Server 2013

 


A política de versão do cliente é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.

A implantação de uma ou mais políticas de versão de cliente por usuário é opcional. Você também pode implantar apenas uma política de versão do cliente global ou nível do site ou políticas de versão do cliente no nível do grupo. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Quando nenhuma política específica de nível de site, de nível de grupo ou por usuário é atribuída, os clientes padrão que têm permissão para se registrar no Lync Server 2013 são aqueles definidos na política de versão do cliente global.

Depois de criar pelo menos uma política de versão de cliente por usuário, use os procedimentos neste tópico para atribuir a política que especifica as versões de cliente que você deseja permitir para se registrar no Lync Server.

Para obter detalhes sobre como criar políticas de versão de cliente por usuário, consulte [especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Para atribuir uma política de versão de cliente por usuário

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Use um dos seguintes métodos para localizar um usuário:
    
      - Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.
    
      - Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.

5.  (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
    1.  Clique em **Adicionar filtro**.
    
    2.  Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.
    
    3.  Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
    4.  Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

    
    5.  Clique em **Localizar**.

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.
    

    > [!TIP]  
    > Se quiser que a mesma política de versão de cliente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de versão do cliente**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.

    
      - Permitir que o Lync Server escolha automaticamente a política de nível global ou, se definida, a política de nível de site ou política de nível de pool.
    
      - Clique no nome de uma política de versão de cliente por usuário definida anteriormente na página de **política de versão do cliente** .
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.



8.  Ao concluir, clique em **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Atribuir uma política de versão de cliente por usuário usando cmdlets do Windows PowerShell

Você pode atribuir políticas de versão de cliente por usuário usando o cmdlet Grant-CsClientVersionPolicy. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Para atribuir uma política de versão de cliente por usuário a um único usuário

  - O comando a seguir atribui a política de versão do cliente por usuário RedmondClientVersionPolicy ao usuário Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Para atribuir uma política de versão de cliente por usuário a vários usuários

  - Esse comando atribui a política de política de cliente por usuário RedmondClientVersionPolicy a todos os usuários que atualmente recebem a política de voz RedmondVoicePolicy. Para obter mais informações sobre o parâmetro Filter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Para cancelar a atribuição de uma política de versão de cliente por usuário

  - O comando a seguir cancela a atribuição de qualquer política de versão de cliente por usuário atribuída anteriormente a Ken Myer. Após a atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global, sua política de site local (se houver) ou a política de escopo de serviço atribuída ao registrador. Uma política de escopo de serviço tem precedência sobre qualquer política de site e uma política de site tem precedência sobre a política global.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Como atribuir políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

