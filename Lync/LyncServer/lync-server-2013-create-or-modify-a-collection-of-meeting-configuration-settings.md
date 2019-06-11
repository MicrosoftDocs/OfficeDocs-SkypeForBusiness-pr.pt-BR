---
title: Criar ou modificar um conjunto de definições de configuração de reunião
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b948d5aded2447e5319378a613fdf474c3e5450
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Criar ou modificar uma coleção de definições de configuração de reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Você pode usar as configurações na página configuração de reunião para definir várias características da experiência de participação na reunião. Por padrão, as configurações globais definem a experiência de junção. Você também pode criar configurações em nível de site e de junção de reunião no nível do grupo. Se você criar configurações no nível de pool, elas serão aplicadas a todas as reuniões hospedadas pelo pool. Se você não criar configurações no nível de pool, as configurações do nível local serão aplicadas, caso existam. Se você não definir as configurações de nível local, as configurações globais serão aplicadas a todas as reuniões.

<div>

## <a name="to-create-new-meeting-join-settings"></a>Para criar novas configurações de junção de reunião

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.

4.  Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:
    
      - Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e, em seguida, clique em **OK**.
    
      - Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e, em seguida, clique em **OK**.

5.  Para direcionar os participantes que ligam de um PSTN através do lobby, desmarque a caixa de seleção  **Chamadores PSTN ignoram o lobby**. Por padrão, os participantes discando pelo PSTN irão diretamente para a reunião.

6.  Para configurar quem pode ser um apresentador na reunião, em **Designar como apresentador**, siga um dos procedimentos abaixo:
    
      - Para não permitir que qualquer pessoa além do organizador seja o apresentador, clique em **Nenhum**.
    
      - Para permitir que apenas participantes membros da sua organização sejam apresentadores, clique em **Empresa**. Esta é a configuração padrão.
    
      - Para permitir que qualquer participante seja o apresentador, clique em **Todos**.

7.  Para que o organizador selecione um tipo de conferência ao programar uma reunião, desmarque a caixa de seleção  **Tipo de conferência atribuída por padrão**. Por padrão, o tipo de conferência é atribuído automaticamente.

8.  Para evitar que usuários anônimos (não autenticados) sejam aceitos automaticamente, desmarque a caixa de seleção **Aceitar usuários anônimos por padrão**. Por padrão, os usuários anônimos são aceitos automaticamente nas reuniões.

9.  Para personalizar o convite da reunião enviado para os participantes, faça o seguinte. Observe que o comprimento máximo das URLs e o texto do rodapé padrão é de 1KB. Exceto para a **URL de ajuda**, se você não especificar um valor para as personalizações, elas não serão incluídas na reunião. Se você não incluir uma URL de ajuda personalizada, a URL da ajuda padrão do Lync será exibida no convite.
    
      - Para personalizar o logotipo exibido no convite da reunião, na **URL do Logotipo**, insira o local do logotipo.
        
        <div>
        

        > [!NOTE]
        > O logotipo deve ser uma imagem GIF ou JPG com um tamanho de 188 por 30 pixels.

        
        </div>
    
      - Para personalizar o texto de ajuda exibido no convite da reunião, na **URL de ajuda**, insira o local do texto de ajuda.
    
      - Para personalizar o texto legal exibido no convite da reunião, na **URL do texto legal**, insira o texto legal.
    
      - Para personalizar o texto do rodapé exibido no convite da reunião, em **Texto do rodapé personalizado**, insira o texto.

10. Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>Para modificar uma coleção existente de configurações de reunião

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.

4.  Na lista de configurações da reunião, clique na configuração que deseja alterar, em **Editar** e, em seguida, clique em **Exibir detalhes**.

5.  Em **Editar configuração da reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando novas definições de configuração de reunião usando cmdlets do Windows PowerShell

As configurações de reunião podem ser criadas (somente no escopo do site) usando o Windows PowerShell e o cmdlet New-CsMeetingConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>Para criar definições de configuração de reunião que usam os valores padrão

  - Esse comando cria um novo conjunto de definições de configuração de reunião para o site Redmond:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Como não há parâmetros (além do parâmetro obrigatório Identity) onde especificado no comando anterior, as novas definições de configuração de reunião usarão os valores padrões para todas as suas propriedades.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>Para alterar um valor de propriedade ao criar definições de configuração de reunião

  - Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de reuniões de configuração da reunião que, por padrão, permite todos em uma reunião serem apresentadores a usarem um comando como este:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>Para alterar vários valores de propriedade ao criar definições de configuração de reunião

  - Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, esse comando admite todas as pessoas em uma reunião como apresentador e também obriga os usuários de PSTN a aguardar no lobby até que sejam formadas de forma reconhecidas para a reunião:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

