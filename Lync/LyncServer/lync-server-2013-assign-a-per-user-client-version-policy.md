---
title: 'Lync Server 2013: atribuir uma política de versão do cliente por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3668e21836fd3ecee0740493c8b9bd631227583a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029262"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Atribuir uma política de versão de cliente por usuário no Lync Server 2013

 


A política de versão do cliente é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.

Implantar uma ou mais políticas de versão do cliente por usuário é opcional. Também é possível implantar apenas uma política de versão do cliente a nível global ou políticas de versão do cliente a nível do pool ou a nível do site. Se você implantar políticas por usuário, deve atribui-las explicitamente aos usuários, grupos ou objeto de contato. Quando nenhuma política específica no nível do site, no nível do pool ou por usuário é atribuída, os clientes padrão que têm permissão para se registrar no Lync Server 2013 são aqueles definidos na política de versão do cliente de nível global.

Depois de criar pelo menos uma política de versão do cliente por usuário, use os procedimentos neste tópico para atribuir a política que especifica as versões do cliente que você deseja permitir o registro no Lync Server.

Para obter detalhes sobre como criar políticas de versão do cliente por usuário, consulte [especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Para atribuir uma política de versão do cliente por usuário

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
    > Se você deseja que a mesma política de versão do cliente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.



7.  Em **Atribuir políticas**, em **Política de versão do cliente**, faça um dos seguintes:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.

    
      - Permitir que o Lync Server escolha automaticamente a política de nível global ou, se definida, a política de nível de site ou política de nível de pool.
    
      - Clique no nome de uma política de versão do cliente por usuário definida anteriormente na página **Política de versão do cliente**.
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos e permissões do usuário definidos na política.



8.  Quando terminar, clique em **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de versão do cliente por usuário usando cmdlets do Windows PowerShell

Também é possível atribuir políticas de versão do cliente específicas do usuário usando o cmdlet Grant-CsClientVersionPolicy. Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Para atribuir uma política de versão do cliente específica do usuário

  - O comando a seguir atribui a política de versão do cliente RedmondClientVersionPolicy ao usuário Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Para atribuir uma política de versão do cliente específica do usuário a vários usuários

  - Este comando atribui a política de versão do cliente RedmondClientVersionPolicy a todos os usuários aos quais a política de voz RedmondVoicePolicy tiver sido anteriormente atribuída. Para obter mais informações sobre o parâmetro Filter usado nesse comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Para cancelar a atribuição de uma política de versão do cliente específica do usuário

  - O comando a seguir cancela a atribuição de uma política de versão do cliente específica do usuário atribuída anteriormente a Ken Myer. Após cancelar a atribuição de uma política específica do usuário, o Ken Myer será automaticamente gerenciado usando a política global, sua política do site local (se existir) ou a política de escopo de serviço atribuída ao seu Registrar. Uma política de escopo de serviço tem precedência sobre qualquer política de site e a política de site tem precedência sobre a política global.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

