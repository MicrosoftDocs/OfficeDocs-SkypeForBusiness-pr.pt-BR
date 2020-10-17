---
title: 'Lync Server 2013: atribuir uma política de PIN por usuário'
description: 'Lync Server 2013: atribua uma política de PIN por usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1148a015ba9b2c173f6e23ceeb4d3b37c6ac55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563587"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a>Atribuir uma política de PIN por usuário no Lync Server 2013

 


A política de PIN (número de identificação pessoal) de conferência discada é uma das configurações individuais de uma conta de usuário que pode ser configurada no painel de controle do Lync Server 2013.

A implantação de uma ou mais políticas de PIN por usuário é opcional. Também é possível implantar somente uma política de PIN de nível global ou política de PIN de nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Direitos e permissões do usuário relacionados ao uso de PINs para conferência discada assumem automaticamente o padrão daqueles definidos na política de PIN de nível global quando nenhuma política específica de nível de site ou por usuário é atribuída.

Após a criação de pelo menos uma política de PIN por usuário, use o procedimento neste tópico para atribuir a política que especifica as restrições que você deseja que o servidor imponha sobre os PINs criados e usados por um usuário específico.

Para obter detalhes sobre como criar políticas de PIN de conferência discada por usuário, confira [criar ou modificar as configurações de PIN de conferência discada no Lync Server 2013 para um site ou grupo de usuários](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## <a name="to-assign-a-per-user-pin-policy"></a>Para atribuir uma política de PIN por usuário

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

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e clique em **Atribuir políticas**.
    

    > [!TIP]  
    > Se você quiser a mesma política de PIN por usuário aplicada a diversos usuários, selecione múltiplos usuários nos resultados da pesquisa e clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.



7.  Em **Atribuir Políticas**, em **Política de PIN**, execute uma das seguintes ações:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt; manter como está &gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.

    
      - Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política PIN por usuário definida anteriormente na página **Política de PIN**.
        

        > [!TIP]  
        > Para ajudá-lo a decidir a política que você deseja atribuir, após clicar em um nome de política, clique em <STRONG>Exibir</STRONG> para exibir os direitos e permissões de usuário definidos na política.



8.  Quando terminar, clique em **OK**.

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de PIN de Per-User usando cmdlets do Windows PowerShell

Você pode atribuir políticas de PIN por usuário usando o Windows PowerShell e o cmdlet **Grant-CsPinPolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Para atribuir uma política PIN por usuário para um único usuário

  - O seguinte comando atribui a política PIN por usuário RedmondPinPolicy para o usuário Ken Myer.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Para atribuir uma política PIN por usuário a vários usuários

  - O seguinte comando atribui a política PIN por usuário RedmondUsersPinPolicy para todos os usuários que trabalham na cidade de Redmond. Para obter detalhes sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a>Para retirar a atribuição de uma política PIN por usuário

  - O seguinte comando retira a atribuição de qualquer política PIN por usuário anteriormente atribuído ao Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter detalhes, consulte [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).

## <a name="see-also"></a>Confira também


[Criar uma nova política de PIN no Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  


[Atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

