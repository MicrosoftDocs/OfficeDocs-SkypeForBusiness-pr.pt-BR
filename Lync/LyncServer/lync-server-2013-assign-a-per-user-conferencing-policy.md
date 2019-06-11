---
title: 'Lync Server 2013: atribuir uma política de conferência por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dbeb129ef58c6993d1cd919b03d7417d35b439a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836918"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Atribuir uma política de conferência por usuário no Lync Server 2013

 


A política de conferência é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.

Implantar uma ou mais políticas de conferência por usuário é opcional. Você também pode implantar apenas uma política de conferência de nível global ou de conferência no nível do site. Se você implantar políticas por usuário, deverá atribuí-las explicitamente a usuários, grupos ou objetos de contato. Permissões e direitos de usuário de conferência automaticamente são padrão para aqueles definidos na política de conferência de nível global quando nenhuma política específica de nível de site ou por usuário é atribuída.

Depois de criar pelo menos uma política de conferência por usuário, use os procedimentos neste tópico para atribuir a política que especifica os direitos de usuário e as permissões que você deseja que o servidor conceda às reuniões organizadas por um usuário específico.

Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Para obter detalhes sobre como criar políticas de conferência, consulte [criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Para atribuir uma política de conferência por usuário

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
    > Se quiser que a mesma política de conferência por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de conferência**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.

    
      - Selecione ** \<automático\> ** para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de conferência por usuário que você definiu anteriormente na página da **política de conferência** .
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.



8.  Ao concluir, clique em **OK**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Atribuir uma política de conferência por usuário usando cmdlets do Windows PowerShell

Políticas de conferência por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsConferencingPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Para atribuir uma política de conferência por usuário a um único usuário

  - O comando a seguir atribui a RedmondConferencingPolicy de política de conferência por usuário ao usuário Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Para atribuir uma política de conferência por usuário a vários usuários

  - Esse comando atribui a política de conferência por usuário HRConferencingPolicy a todos os usuários que trabalham para o departamento de recursos humanos. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Para cancelar a atribuição de uma política de conferência por usuário

  - O comando a seguir não atribui a atribuição de nenhuma política de conferência por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Como atribuir políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

