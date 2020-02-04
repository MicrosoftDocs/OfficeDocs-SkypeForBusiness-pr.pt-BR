---
title: 'Lync Server 2013: definir o PIN de conferência discada do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab97b3efe350ef82527262103e9b00104990245a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Definir o PIN de conferência discada de um usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-10_

Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Lync Server 2013 com as credenciais dos serviços de domínio Active Directory (AD DS) requer um PIN (número de identificação pessoal). Se um usuário esquecer o PIN de conferência discada ou não tiver definido o PIN usando o Lync Server, você poderá definir o PIN do usuário no painel de controle do Lync Server. Você pode gerar automaticamente o PIN ou criá-lo manualmente.

<div>


> [!NOTE]  
> Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política. Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais. Para obter detalhes sobre como configurar uma política de PIN, consulte <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurar regras de PIN (número de identificação pessoal) da conferência discada no Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Para definir o PIN de um usuário

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
    
    4.  Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.
        
        <div>
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

        
        </div>
    
    5.  Clique em **Localizar**.
    
    <div>
    

    > [!NOTE]  
    > Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em <STRONG>Ação</STRONG> e depois em <STRONG>Desbloquear PIN</STRONG>.

    
    </div>

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.

7.  Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:
    
      - Para permitir que o Lync Server 2013 gere o PIN do usuário, selecione **gerar automaticamente um PIN válido** (o padrão).
    
      - Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.

8.  Clique em **OK**.

9.  Em **Definir PIN**, siga um destes procedimentos:
    
      - Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.
    
      - Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.

10. Clique em **Fechar**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Atribuir um PIN do usuário usando cmdlets do Windows PowerShell

Você pode atribuir números PIN utilizando o cmdlet Set-CsClientPin. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para atribuir automaticamente um número PIN a um usuário

  - O comando a seguir atribui um número PIN ao usuário Ken Myer. Como o parâmetro PIN não está incluído, o Lync Server gerará e atribuirá automaticamente o número do PIN.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para atribuir um número PIN específico a um usuário

  - Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Número de Acesso de Discagem](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))  


[Configurar regras de PIN (número de identificação pessoal) da conferência discada no Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

