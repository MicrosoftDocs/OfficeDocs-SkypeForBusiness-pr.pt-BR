---
title: Configurar o cliente Skype for Business no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a78e229b54ec165897d920d8f04db49451eac9b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configurar a experiência do cliente com o Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-09-17_

**Resumo:** Este tópico descreve como configurar a experiência do cliente para usuários clientes do Skype for Business em um ambiente do Lync Server 2013. Você pode configurar a experiência do cliente somente se você estiver executando o Lync Server 2013 com a atualização cumulativa de dezembro de 2014 (5.0.8308.857) ou posterior instalada. Para obter informações sobre como atualizar o Lync Server 2013, consulte [atualizações para o Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).

O Skype for Business oferece uma nova experiência de usuário que se baseia na experiência do produto consumidor do Skype. Além de todos os recursos do Lync, o Skype for Business oferece novos recursos com controles simplificados e ícones conhecidos. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync agora é Skype for Business – Veja o que há de novo](https://go.microsoft.com/fwlink/?linkid=529022).

O Lync Server 2013 oferece suporte à nova experiência de cliente do Skype for Business, bem como à experiência de cliente do Lync. Como administrador, você pode escolher a experiência de cliente preferencial para seus usuários. Por exemplo, você pode querer implantar a experiência de cliente do Lync até que os usuários em sua organização sejam totalmente treinados na nova experiência do Skype for Business. Ou, se você ainda não tiver atualizado todos os usuários para o Skype for Business Server 2015, talvez queira que todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.

<div>


> [!IMPORTANT]  
> Se sua organização tiver o Skype for Business Server 2015 e o Lync Server 2013 implantados, a experiência do cliente padrão será diferente, dependendo das versões do servidor e das configurações da interface do usuário. Quando os usuários iniciam o Skype for Business pela primeira vez, eles sempre verão a interface de usuário do Skype for Business, mesmo que você tenha selecionado a interface de usuário do Lync. Após alguns minutos, os usuários são solicitados a alternar para o modo Lync. Para obter mais informações, consulte <STRONG>primeiro início do comportamento de cliente</STRONG> mais adiante neste tópico.



</div>

<div>


> [!NOTE]  
> A experiência de cliente do Lync 2013 não é uma opção para as versões do cliente do Skype for Business 2016. Antes de tentar configurar seu ambiente de cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não inicie com o número 16; por exemplo: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configurar a experiência do cliente

Você pode especificar a experiência do cliente que os usuários da sua organização verão usando o cmdlet **set-CSClientPolicy** com o parâmetro EnableSkypeUI. O comando a seguir seleciona a experiência de cliente do Skype for Business para todos os usuários da sua organização afetados pela política global (Lembre-se, políticas específicas de site ou usuário substituem a política global):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

O próximo comando seleciona a experiência de cliente do Lync para todos os usuários da sua organização afetados pela política global:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

O próximo comando seleciona a experiência de cliente do Skype for Business para todos os usuários no site de Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Se você quiser configurar a experiência do cliente para usuários específicos dentro da sua organização, você pode criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e, em seguida, atribuir a política a usuários específicos usando o cmdlet **Grant-CsClientPolicy** .

Por exemplo, o seguinte comando cria uma nova política de cliente, SalesClientUI, que seleciona a experiência de cliente do Skype for Business:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

O próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de vendas:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Primeiro iniciar comportamentos do cliente

Por padrão, quando os usuários iniciam o Skype for Business pela primeira vez, eles sempre verão a interface de usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync Configurando o valor do $False parâmetro EnableSkypeUI como descrito anteriormente . Após alguns minutos, os usuários serão solicitados a alternar para o modo Lync.

Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes que o cliente seja iniciado pela primeira vez após a atualização:

1.  Confirme se o valor de `EnableSkypeUI` está definido como $false na política que você está usando, conforme descrito anteriormente.

2.  Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes da primeira vez que os usuários iniciam o cliente Skype for Business e você deve fazer isso apenas uma vez. Para obter informações sobre como criar um objeto de diretiva de grupo para atualizar o registro em um computador ingressado no domínio, consulte a seção mais adiante neste tópico.
    
    Na chave ** \[hKey\_Current\_user\\software\\\\\\Office Lync\] ** , crie um novo valor **binário** .
    
    O **nome do valor** deve ser **EnableSkypeUI**, e os **dados do valor** devem ser definidos como **00 00 00 00**.
    
    A chave deve ter a seguinte aparência:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

A interface de usuário do Lync agora será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar a exibição do tutorial de tela de boas-vindas

Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclui *7 dicas rápidas que a maioria das pessoas pede*. Você pode desativar a exibição da tela de boas-vindas, mas ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do registro no computador cliente:

Na chave ** \[de\_software\_\\do\\usuário atual\\do\\Microsoft\\Office\] 15,0 Lync** , crie um novo **valor de DWORD (32 bits)**. O **nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **dados do valor** devem ser definidos como **1**.

A chave deve ter a seguinte aparência:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Desativar o tutorial do cliente

Se você não quiser que os usuários possam acessar o tutorial, desative o tutorial do cliente com o seguinte valor de registro:

Na chave ** \[de\_software\_\\do\\usuário atual\\do\\Microsoft\\Office\] 15,0 Lync** , crie um novo **valor de DWORD (32 bits)**. O **nome do valor** deve ser **TutorialFeatureEnabled**, e os **dados do valor** devem ser definidos como **0**.

    "TutorialFeatureEnabled"=dword:00000000

Você pode ativar o tutorial novamente definindo os dados do **valor** como **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Experiências de cliente padrão

Se sua organização tiver o Skype for Business Server 2015 e o Lync Server implantados, a experiência do cliente será diferente, dependendo das versões do servidor e da configuração da interface do usuário do Skype. A tabela a seguir mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versão do servidor</p></th>
<th><p>Configuração EnableSkypeUI</p></th>
<th><p>Experiência do cliente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Padrão</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Falso</p></td>
<td><p>O usuário é solicitado a alternar para o modo Lync (o usuário pode mudar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>Padrão</p></td>
<td><p>O usuário é solicitado a alternar para o modo Lync (o usuário pode mudar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>Falso</p></td>
<td><p>O usuário é solicitado a alternar para o modo Lync (o usuário pode mudar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sem patches)</p></td>
<td><p>Padrão</p></td>
<td><p>O usuário é solicitado a alternar para a experiência de cliente do Lync (o usuário não pode mudar para o Skype for Business mais tarde)</p></td>
</tr>
</tbody>
</table>


A próxima tabela mostra a experiência do cliente quando o administrador altera a configuração inicial da experiência da interface do usuário do Skype:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versão do servidor</p></th>
<th><p>Configuração da interface do usuário do Skype</p></th>
<th><p>UI de cliente = Lync</p></th>
<th><p>UI de cliente = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>O usuário é solicitado a alternar para o Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Falso</p></td>
<td><p>IU do Lync</p></td>
<td><p>O usuário é solicitado a alternar para a interface do usuário do Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>True</p></td>
<td><p>O usuário é solicitado a alternar para o Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>Falso</p></td>
<td><p>IU do Lync</p></td>
<td><p>O usuário é solicitado a alternar para a interface do usuário do Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sem patches)</p></td>
<td><p>Padrão</p></td>
<td><p>Modo do Lync (não é possível mudar para o Skype for Business)</p></td>
<td><p>IU do Lync (não é possível mudar para o Skype for Business)</p></td>
</tr>
</tbody>
</table>


As versões de patch necessárias para gerenciar a configuração do cliente Skype for Business são:

  - Lync Server 2010-atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010. Para obter informações, consulte [atualizações para o Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013. Para obter informações, consulte [atualizações para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Criar um objeto de diretiva de grupo para modificar o registro em um computador ingressado no domínio

A atualização do registro para exibir a experiência do cliente do Lync na primeira vez que um usuário inicia o cliente Skype for Business deve ser feita apenas uma vez. Se você usar um objeto de política de grupo (GPO) para atualizar o registro, será necessário definir o objeto para criar um novo valor em vez de atualizar os dados de valor. Quando o GPO for aplicado, se o novo valor não existir, o GPO o criará e definirá os dados do valor como 0.

O procedimento a seguir descreve como modificar o registro para que a experiência de cliente do Lync seja exibida na primeira vez que um usuário iniciar o Skype for Business. Você também pode usar este procedimento para atualizar o registro para desabilitar o tutorial de tela de boas-vindas, conforme descrito anteriormente.

**Para criar o GPO**

1.  Inicie o **console de gerenciamento de política de grupo**.
    
    Para obter informações sobre como usar o console de gerenciamento de política de grupo, consulte [console de gerenciamento de política de grupo](https://go.microsoft.com/fwlink/?linkid=532759).

2.  Clique com o botão direito do mouse no nó **objetos de política de grupo** e selecione **novo** no menu.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o GPO, por exemplo, **MakeLyncDefaultUI**, e clique em **OK**.

4.  Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.

5.  No **Editor de gerenciamento de política de grupo**, expanda Configuração do **usuário**, **preferências**, expanda **configurações do Windows**e selecione o nó **registro** .

6.  Clique com o botão direito do mouse no nó **do registro** e selecione **novo** \> **item do registro**.

7.  Na caixa de diálogo **novas propriedades do registro** , atualize o seguinte:
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Campo</th>
    <th>Valor a ser selecionado ou inserido</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Ação</strong></p></td>
    <td><p><strong>Create</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Hive</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Caminho da chave</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value name</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Value type</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Dados de valor</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Clique em **OK** para salvar suas alterações e, em seguida, feche o GPO.

Em seguida, você precisará vincular o GPO que você criou ao grupo de usuários ao qual você deseja atribuir a política, como uma OU.

**Para usar o GPO para atribuir a política**

1.  No console de gerenciamento de política de grupo, clique com o botão direito do mouse na UO à qual você deseja atribuir a política e, em seguida, selecione **vincular a um GPO existente**.

2.  Na caixa de diálogo **selecionar GPO** , selecione o GPO que você criou e, em seguida, selecione **OK**.

3.  No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:
    
    **gpupdate/target: User**
    
    A mensagem "Atualizando a política..." é exibido enquanto o GPO é aplicado. Quando ela é concluída, a mensagem "a atualização da política de usuário foi concluída com êxito" é exibida.

4.  No prompt de comando, digite o seguinte comando: 
    
    **Gpresult/r**
    
    Você deve ver "objetos de política de grupo atribuídos" com o nome do GPO que você criou exibido abaixo.

Você também pode verificar se o GPO atualizou com êxito o registro no computador de um usuário examinando o registro. Abra o editor do registro e navegue até a chave do ** \[\_\\\\Office\\Lync\] atual\_software do usuário\\do hKey** . Se o GPO atualizou com êxito o registro, você verá um valor chamado EnableSkypeUI com um valor de 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

