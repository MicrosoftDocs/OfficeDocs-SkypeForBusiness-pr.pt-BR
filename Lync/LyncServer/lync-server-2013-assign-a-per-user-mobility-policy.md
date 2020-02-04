---
title: 'Lync Server 2013: atribuir uma política de mobilidade por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20b5929959e87f4a39c69ab09f7836a471e16b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722841"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Atribuir uma política de mobilidade por usuário no Lync Server 2013

 


A política de mobilidade é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server ou no Shell de gerenciamento do Lync Server.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Para atribuir uma política de mobilidade por usuário com o painel de controle do Lync Server

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
    > Se quiser que a mesma política de mobilidade por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de mobilidade**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.

    
      - Selecione ** \<automático\> ** para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de mobilidade por usuário definida anteriormente na página da **política de mobilidade** .
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.



8.  Ao concluir, clique em **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Atribuir uma política de mobilidade por usuário usando cmdlets do Windows PowerShell

Você pode atribuir políticas de mobilidade por usuário usando o Windows PowerShell e o cmdlet **Grant-CsMobilityPolicy** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Para atribuir uma política de mobilidade por usuário a um único usuário

  - O comando a seguir atribui a RedmondMobilityPolicy de política de mobilidade por usuário ao usuário Ken Myer.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Para atribuir uma política de mobilidade por usuário a vários usuários

  - O comando a seguir atribui a política de mobilidade por usuário RedmondMobilityPolicy a todos os usuários que atualmente recebem a política NorthAmericaMobilityPolicy. Para obter detalhes sobre o parâmetro de filtro usado neste comando, consulte [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Para cancelar a atribuição de uma política de mobilidade por usuário

  - O comando a seguir não atribui atribuições de política de mobilidade por usuário anteriormente atribuídas a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter detalhes, consulte [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Confira também


[Configurando a política de mobilidade no Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

