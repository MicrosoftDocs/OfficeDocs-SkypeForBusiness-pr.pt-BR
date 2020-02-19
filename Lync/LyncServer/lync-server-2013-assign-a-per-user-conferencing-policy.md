---
title: 'Lync Server 2013: atribuir uma política de conferência por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47419dfde4bf41b0edfccb2bce23393f04c49a3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134447"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Atribuir uma política de conferência por usuário no Lync Server 2013

 


A política de conferência é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.

A implantação de uma ou mais políticas de conferência por usuário é opcional. Você também pode implantar somente uma política de conferência a nível global ou política de conferência a nível de site. Se você implantar políticas por usuário, deverá explicitamente atribuí-las a usuários, grupos ou objetos de contato. As permissões e direitos de usuário de conferência são automaticamente padrão para os que estão definidos na política de conferência a nível global, quando nenhuma política específica a nível de site ou por usuário é atribuída.

Depois de criar pelo menos uma política de conferência por usuário, use os procedimentos neste tópico para atribuir a política que especifica os direitos e permissões que você deseja que o servidor conceda a reuniões organizadas por um determinado usuário.

Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Para obter detalhes sobre como criar políticas de conferência, consulte [create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Para atribuir uma plítica de conferência por usuário

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

6.  Clique em um usuário nos resultados da pesquisa, em **Ação** e em **Atribuir políticas**.
    

    > [!TIP]  
    > Se deseja que a mesma política de conferência por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa e clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.



7.  Em **Atribuir políticas**, na **Política de conferência**, faça o seguinte procedimento:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.

    
      - Selecione ** \<automático\> ** para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de conferência por usuário previamente definida na página **Política de conferência**.
        

        > [!TIP]  
        > Para ajudar você a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para exibir os direitos e permissões do usuário definidos na política.



8.  Quando terminar, clique em **OK**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de conferência por usuário usando cmdlets do Windows PowerShell

As políticas de conferência por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsConferencingPolicy. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Para atribuir uma política de conferência por usuário a um único usuário

  - O comando a seguir atribui a política de conferência por usuário RedmondConferencingPolicy ao usuário Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Para atribuir uma política de conferência por usuário a vários usuários

  - Este comando atribui a política de conferência por usuário HRConferencingPolicy a todos os usuários que trabalham para o departamento de Recursos Humanos. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Para cancelar a atribuição de uma política de conferência por usuário

  - O comando a seguir cancela a atribuição de qualquer política de conferência por usuário atribuída a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global ou a política de site local (se houver). Um política de site tem prioridade sobre a política global.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

