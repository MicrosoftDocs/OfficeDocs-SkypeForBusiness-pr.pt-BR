---
title: 'Lync Server 2013: atribuir uma política de arquivamento por usuário'
description: 'Lync Server 2013: atribua uma política de arquivamento por usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559987"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Atribuir uma política de arquivamento por usuário no Lync Server 2013

 


A política de arquivamento é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server 2013.

A implantação de uma ou mais políticas de arquivamento por usuário é opcional. Você também pode implantar apenas uma política de arquivamento de nível global ou política de arquivamento em nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente a usuários, grupos ou objetos de contato. Os requisitos de arquivamento são automaticamente padrão para aqueles definidos na política de conferência de nível global quando não há uma política específica de nível de site ou por usuário atribuída.

Depois de criar pelo menos uma política de arquivamento por usuário, use os procedimentos neste tópico para atribuir a política que especifica apropriadamente se as comunicações internas de um usuário específico, as comunicações externas ou ambas, serão arquivadas pelo servidor.

Para obter detalhes sobre como criar políticas de arquivamento por usuário, consulte [criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>Para atribuir uma política de arquivamento por usuário

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
    > Se você deseja que a mesma política de arquivamento por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de arquivamento**, execute um dos seguintes procedimentos:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt; manter como está &gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.

    
      - Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de arquivamento por usuário definida anteriormente na página **política de arquivamento** .
        

        > [!TIP]  
        > Para ajudar a decidir qual política você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos de usuário e as permissões definidas.



8.  Quando terminar, clique em **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de arquivamento de Per-User usando cmdlets do Windows PowerShell

Você pode atribuir políticas de arquivamento por usuário usando o Windows PowerShell e o cmdlet **Grant-CsArchivingPolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Para atribuir uma política de arquivamento por usuário a um único usuário

  - O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Para atribuir uma política de arquivamento por usuário a vários usuários

  - Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que têm contas hospedadas no pool de registradores atl-cs-001.litwareinc.com. Para obter mais informações sobre o parâmetro Filter usado nesse comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>Para cancelar a atribuição de uma política de arquivamento por usuário

  - O comando a seguir cancela a atribuição de todas as políticas de arquivamento por usuário atribuídas anteriormente a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado pela política global ou pela política de seu site local (se houver uma). Uma política de site prevalece sobre a política global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-create-archiving-policy-sites-users.md)  


[Atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

