---
title: 'Lync Server 2013: atribuir uma política de local por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a53ae779ccc6fb19bb2d16274e007b8fc405c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739391"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Atribuir uma política de localização por usuário no Lync Server 2013

 


A política de localização é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.

Implantar uma ou mais políticas de localização por usuário é opcional. Você também pode implantar apenas uma política de localização de nível global ou uma política de localização em nível de sub-rede. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. As configurações avançadas do 9-1-1 (E9-1-1) são automaticamente padrão para as definidas na política de localização de nível global quando nenhuma política específica de nível de sub-rede ou por usuário é atribuída.

Depois de criar pelo menos uma política de localização por usuário, use os procedimentos deste tópico para atribuir à política que especifica as configurações que você deseja que o servidor aplique para as chamadas de emergência feitas por um usuário específico.

Para obter uma lista de todas as configurações de política de localização disponíveis, consulte [definindo a política de localização do Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Para obter detalhes sobre como criar políticas de localização, consulte [criar políticas de localização no Lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Para atribuir uma política de local por usuário com o painel de controle do Lync Server

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
    > Se você quiser que a mesma política de localização por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de localização**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.

    
      - Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de sub-rede.
    
      - Clique no nome de uma política de local por usuário que você definiu anteriormente executando o cmdlet **New-CsLocationPolicy** .
        

        > [!TIP]  
        > Para ajudá-lo a decidir a política que você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos do usuário e as permissões definidas na política.



8.  Ao concluir, clique em **OK**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Atribuir uma política de local por usuário usando cmdlets do Shell de gerenciamento do Lync Server

Você pode atribuir políticas de localização por usuário usando o cmdlet Grant-CsLocationPolicy. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>Para atribuir uma política de localização por usuário a um único usuário

  - O comando a seguir atribui a RedmondLocationPolicy de política de localização por usuário ao usuário Ken Myer.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>Para atribuir uma política de local por usuário a vários usuários

  - Esse comando atribui a política de localização por usuário AccountingDepartmentLocationPolicy a todos os usuários que trabalham para o departamento de contabilidade. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>Para cancelar a atribuição de uma política de local por usuário

  - O comando a seguir não atribui atribuições de política de local por usuário anteriormente atribuídas a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .

