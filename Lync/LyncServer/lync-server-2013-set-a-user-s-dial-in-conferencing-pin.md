---
title: 'Lync Server 2013: definir PIN de conferência discada de um usuário'
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
ms.openlocfilehash: 44404565dd36b89ebfed78e1caf6223782bdf434
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Definir PIN de conferência discada de um usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-10_

Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Lync Server 2013 com credenciais do AD DS (serviços de domínio Active Directory) requer um PIN (número de identificação pessoal). Se um usuário esquecer o PIN de conferência discada ou não tiver definido o PIN usando o Lync Server, você poderá definir o PIN do usuário no painel de controle do Lync Server. Você pode gerar automaticamente o PIN ou criá-lo manualmente.

<div>


> [!NOTE]  
> Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política. Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais. Para obter detalhes sobre como configurar uma política de PIN, consulte <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurar regras de PIN (número de identificação pessoal) de conferência discada no Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Para definir o PIN de um usuário

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
    
    4.  Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.
        
        <div>
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

        
        </div>
    
    5.  Clique em **Localizar**.
    
    <div>
    

    > [!NOTE]  
    > Se o PIN estiver bloqueado, você deverá desbloquear o PIN para que possa defini-lo. Para desbloquear o PIN, clique no usuário, clique em <STRONG>Ação</STRONG> e em <STRONG>Desbloquear PIN</STRONG>.

    
    </div>

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.

7.  Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:
    
      - Para permitir que o Lync Server 2013 gere o PIN do usuário, selecione **gerar automaticamente um PIN válido** (padrão).
    
      - Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.

8.  Clique em **OK**.

9.  Em **Definir PIN**, siga um destes procedimentos:
    
      - Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.
    
      - Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.

10. Clique em **Fechar**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Atribuindo um PIN do usuário usando cmdlets do Windows PowerShell

Você pode atribuir números de PIN também podem ser atribuídos usando o cmdlet Set-CsClientPin. Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para atribuir automaticamente um número PIN a um usuário

  - O comando a seguir atribui um número PIN ao usuário Ken Myer. Como o parâmetro PIN não está incluído, o Lync Server gerará e atribuirá automaticamente o número do PIN.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para atribuir um número de PIN específico a um usuário

  - Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Número de Acesso Discado](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[Configurar regras de PIN (número de identificação pessoal) de conferência discada no Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

