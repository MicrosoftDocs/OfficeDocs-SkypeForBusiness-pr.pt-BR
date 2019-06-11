---
title: Configurar o cliente Skype for Business no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa863fd1775fbc2a726806f2dd4fff5fed5dbfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configure the client experience with Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-09-17_

**Resumo:** Este tópico descreve como configurar a experiência do cliente para os usuários do cliente Skype for Business em um ambiente do Lync Server 2013. Você pode configurar a experiência do cliente somente se você estiver executando o Lync Server 2013 com a atualização cumulativa de dezembro de 2014 (5.0.8308.857) ou posterior instalada. Para saber mais sobre como atualizar o Lync Server 2013, confira [atualizações para o Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).

O Skype for Business oferece uma nova experiência de usuário baseada na experiência do produto Skype para consumidores. Além de todos os recursos do Lync, o Skype for Business oferece novos recursos com controles simplificados e ícones conhecidos. Para obter informações detalhadas sobre a nova experiência do cliente, consulte o [Lync agora é o Skype for Business, confira o que há de novo](http://go.microsoft.com/fwlink/?linkid=529022).

O Lync Server 2013 é compatível com a nova experiência de cliente do Skype for Business, bem como com a experiência do cliente do Lync. Como administrador, você pode escolher a experiência do cliente preferida para os seus usuários. Por exemplo, talvez você queira implantar a experiência do cliente do Lync até que os usuários em sua organização sejam totalmente treinados na nova experiência do Skype for Business. Ou, se você ainda não tiver atualizado todos os usuários do Skype for Business Server 2015, talvez queira que todos os usuários tenham a mesma experiência do cliente até que todos sejam atualizados para o novo servidor.

<div>


> [!IMPORTANT]  
> Se a sua organização tiver o Skype for Business Server 2015 e o Lync Server 2013 implantado, a experiência do cliente padrão será diferente, dependendo das versões do servidor e das configurações da interface do usuário. Quando os usuários iniciarem o Skype for Business pela primeira vez, eles verão sempre a interface do usuário do Skype for Business, mesmo que você tenha selecionado a interface do usuário do Lync. Após alguns minutos, os usuários são solicitados a alternar para o modo Lync. Para mais informações, consulte <STRONG>Comportamento do cliente na primeira inicialização</STRONG>, que será abordado neste tópico.



</div>

<div>


> [!NOTE]  
> A experiência do cliente do Lync 2013 não é uma opção para versões do cliente do Skype for Business 2016. Antes de tentar configurar o ambiente do cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não comece com o número 16; por exemplo: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configure the client experience

Você pode especificar a experiência do cliente que os usuários de sua organização verão usando o cmdlet **set-CSClientPolicy** com o parâmetro EnableSkypeUI. O comando a seguir seleciona a experiência do cliente Skype for Business para todos os usuários da sua organização afetados pela política global (Lembre-se de que as políticas específicas do site ou do usuário substituem a política global):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

O próximo comando seleciona a experiência do cliente do Lync para todos os usuários da sua organização afetados pela política global:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

O próximo comando seleciona a experiência do cliente Skype for Business para todos os usuários no site de Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Se você quiser configurar a experiência do cliente para usuários específicos em sua organização, poderá criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e atribuir a política a usuários específicos usando o **Grant-CsClientPolicy** cmdlet.

Por exemplo, o comando a seguir cria uma nova política de cliente, SalesClientUI, que seleciona a experiência do cliente do Skype for Business:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

A próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de Vendas:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Comportamentos do cliente na primeira inicialização

Por padrão, quando os usuários iniciam o Skype for Business pela primeira vez, eles sempre verão a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync definindo o valor do $False parâmetro EnableSkypeUI como descrito anteriormente . Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.

Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:

1.  Confirme se o valor de `EnableSkypeUI` está definido como $false na política que você está usando, conforme descrito anteriormente.

2.  Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes que os novos usuários iniciem o cliente Skype for Business, e deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o registro em um computador que ingressou no domínio, consulte a seção posterior no tópico.
    
    Na chave ** \[hKey\_Current\_user\\software\\Microsoft\\Office\\Lync\] ** , crie um novo valor **binário** .
    
    O **Nome do valor** deve ser **EnableSkypeUI**, e os **Dados do valor** devem ser configurados para **00 00 00 00**.
    
    A chave deve ser semelhante a esta:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

A interface do usuário do Lync será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Tutorial de controle da exibição da tela de boas-vindas

Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclua *7 dicas rápidas que a maioria das pessoas pede*. Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:

Na chave ** \[hKey\_Current\_user\\software\\Microsoft\\Office\\15,0\\Lync\] ** , crie um novo **valor DWORD (32-bit)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser configurados para **1**.

A chave deve ser semelhante a esta:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Desativar o tutorial do cliente

Se você não quiser que os usuários acessem o tutorial, desative o tutorial do cliente com o seguinte valor do Registro:

Na chave ** \[hKey\_Current\_user\\software\\Microsoft\\Office\\15,0\\Lync\] ** , crie um novo **valor DWORD (32-bit)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser configurados para **0**.

    "TutorialFeatureEnabled"=dword:00000000

Você pode reativar o tutorial configurando os **Dados de valor** para **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Experiências de cliente padrão

Se a sua organização tiver o Skype for Business Server 2015 e o Lync Server implantado, a experiência do cliente será diferente, dependendo das versões do servidor e da configuração da interface do usuário do Skype. A seguinte tabela mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:


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
<td><p>False</p></td>
<td><p>O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>Padrão</p></td>
<td><p>O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>False</p></td>
<td><p>O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sem patches)</p></td>
<td><p>Padrão</p></td>
<td><p>O usuário solicitou a mudança para a experiência do cliente do Lync (o usuário não pode mudar para o Skype for Business mais tarde)</p></td>
</tr>
</tbody>
</table>


A tabela a seguir mostra a experiência do cliente quando o administrador muda a configuração inicial para a experiência da interface do usuário do Skype:


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
<th><p>Interface do usuário do cliente = Lync</p></th>
<th><p>Interface do usuário do cliente = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>O usuário pediu que mudar para o Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Interface do usuário do Lync</p></td>
<td><p>Usuário solicitado a alternar para a interface do usuário do Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>True</p></td>
<td><p>O usuário pediu que mudar para o Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 ou Lync Server 2013 (com patches corretos)</p></td>
<td><p>False</p></td>
<td><p>Interface do usuário do Lync</p></td>
<td><p>Usuário solicitado a alternar para a interface do usuário do Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 ou Lync Server 2013 (sem patches)</p></td>
<td><p>Padrão</p></td>
<td><p>Modo Lync (não é possível mudar para o Skype for Business)</p></td>
<td><p>Interface do usuário do Lync (não é possível mudar para o Skype for Business)</p></td>
</tr>
</tbody>
</table>


As versões de patch necessárias para gerenciar a configuração do cliente Skype for Business são:

  - Lync Server 2010-atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010. Para obter informações, consulte [atualizações para o Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013. Para obter informações, consulte [atualizações para o Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crie um Objeto de Política de Grupo para modificar o registro em um computador com ingresso no domínio

A atualização do Registro para exibir a experiência de cliente do Lync na primeira vez que o usuário inicia o cliente Skype for Business deve ser realizada somente uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor. Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0.

O procedimento a seguir descreve como modificar o Registro para que a experiência de cliente do Lync seja exibida na primeira vez que o usuário iniciar o Skype for Business. Você também pode usar este procedimento para atualizar o Registro para desativar o tutorial da tela de boas-vindas conforme descrito anteriormente.

**Para criar o GPO**

1.  Inicie o **Console de Gerenciamento de Política de Grupo**.
    
    Para obter informações sobre como usar o Console de Gerenciamento de Política de Grupo, consulte [Console de Gerenciamento de Política de Grupo](http://go.microsoft.com/fwlink/?linkid=532759).

2.  Clique com o botão direito do mouse no nó **Objetos de Política de Grupo** e selecione **Novo** no menu.

3.  No diálogo **Novo GPO**, insira um nome para o GPO, por exemplo, **MakeLyncDefaultUI**, e clique em **OK**.

4.  Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.

5.  No **Editor de Gerenciamento de Política de Grupo**, expanda **Configuração do Usuário**, **Preferências**, **Configurações do Windows** e selecione o nó **Registro**.

6.  Clique com o botão direito do mouse no nó **do registro** e selecione **novo** \> **item do registro**.

7.  No diálogo **Propriedades do Novo Registro**, atualize as seguintes informações:
    
    
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
    <td><p><strong>Criar</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Hive</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Caminho chave</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Nome do valor</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Tipo de valor</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Dados do valor</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Clique em **OK** para salvar as alterações e feche o GPO.

Em seguida, você precisará vincular o GPO que você criou para o grupo de usuários ao qual a política será atribuída, como uma UO.

**Para usar o GPO para atribuir a política**

1.  No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na UO para a qual você deseja atribuir a política e selecione **Vincular a um GPO existente**.

2.  Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.

3.  No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:
    
    **gpupdate /target:user**
    
    A mensagem "Atualizando a política..." é exibida enquanto o GPO é aplicado. Ao concluir, a mensagem "A atualização da Política de Usuário foi concluída com êxito" é exibida.

4.  No prompt de comando, digite o seguinte comando:
    
    **gpresult /r**
    
    Você deve ver "Objetos de Política de Grupo Atribuídos" com o nome do GPO criado exibido abaixo.

Você também pode verificar se o GPO atualizou com êxito o Registro no computador de um usuário examinando o Registro. Abra o editor do registro e navegue até a chave do grupo de ** \[usuários\] \_\\\\atual do\\\\Office Lync do HKEY.\_** Se o GPO atualizou o Registro com êxito, você verá um valor chamado EnableSkypeUI com o valor 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

