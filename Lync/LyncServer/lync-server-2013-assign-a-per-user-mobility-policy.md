---
title: 'Lync Server 2013: atribuir uma política de mobilidade por usuário'
description: 'Lync Server 2013: atribua uma política de mobilidade por usuário.'
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
ms.openlocfilehash: 9b17c58cf3477002a7fa43035b72c77963663316
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559827"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Atribuir uma política de mobilidade por usuário no Lync Server 2013

 


A política de mobilidade é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server ou no Shell de gerenciamento do Lync Server.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Para atribuir uma política de mobilidade por usuário com o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Utilize um dos métodos a seguir para localizar um usuário:
    
      - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
      - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.

5.  (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
    1.  Clique em **Adicionar filtro**.
    
    2.  Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
    3.  Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
    4.  Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

    
    5.  Clique em **Localizar**.

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.
    

    > [!TIP]  
    > Se você deseja aplicar a mesma política de mobilidade para usuários múltiplos, selecione os usuários nos resultados da pesquisa e clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.



7.  Em **Atribuir políticas**, em **Política de mobilidade**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt; manter como está &gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.

    
      - Selecione esta opção **\<Automatic\>** para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de mobilidade por usuário definida anteriormente na página **Política de mobilidade**.
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos e permissões do usuário definidos na política.



8.  Quando terminar, clique em **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de mobilidade Per-User usando cmdlets do Windows PowerShell

Você pode atribuir políticas de mobilidade por usuário usando o Windows PowerShell e o cmdlet **Grant-CsMobilityPolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Para atribuir uma política de mobilidade por usuário a um único usuário

  - O seguinte comando atribui a política de mobilidade por usuário RedmondMobilityPolicy ao usuário Ken Myer.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Para atribuir uma política de mobilidade por usuário a vários usuários

  - O seguinte comando atribui a política de mobilidade por usuário RedmondMobilityPolicy para todos os usuários atualmente atribuídos com a política NorthAmericaMobilityPolicy. Para obter detalhes sobre o parâmetro Filter usado nesse comando, consulte [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Para retirar a atribuição de uma política de mobilidade por usuário

  - O seguinte comando retira a atribuição de qualquer política de mobilidade por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken Myer será automaticamente gerenciado utilizando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter detalhes, consulte [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Confira também


[Configurando a política de mobilidade no Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

