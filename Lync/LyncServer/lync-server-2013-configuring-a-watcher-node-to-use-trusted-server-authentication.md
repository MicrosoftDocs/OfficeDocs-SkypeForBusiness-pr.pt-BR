---
title: Configurando um nó de inspetor para usar a autenticação de servidor confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configurando um nó de Inspetor no Lync Server 2013 para usar a autenticação de servidor confiável

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Se o seu computador do nó do Inspetor estiver dentro da rede de perímetro, o uso da autenticação de servidor confiável pode reduzir significativamente os impostos da administração para manter um único certificado em vez de várias senhas de conta de usuário.

A primeira etapa na configuração da autenticação do servidor confiável é criar um pool de aplicativos confiável para hospedar o computador do nó do Inspetor. Após a criação do pool de aplicativos confiáveis, você deve configurar transações sintéticas nesse nó do inspetor para executar como um aplicativo confiável.

<div>


> [!NOTE]
> Um aplicativo confiável é um aplicativo que recebe status confiável para ser executado como parte do Lync Server 2013, mas que não é uma parte interna do produto. O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.



</div>

Para criar um pool de aplicativos confiável, abra o Shell de gerenciamento do Lync Server 2013 e execute um comando semelhante a este:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Para obter detalhes sobre os parâmetros usados no comando anterior, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:<BR>Get-Help New-CsTrustedApplicationPool-Full | Saiba



</div>

Depois de criar o pool de aplicativos confiável, configure o computador do nó do inspetor para executar transações sintéticas como um aplicativo confiável. Isso é feito usando-se o cmdlet **New-CsTrustedApplication** e um comando semelhante a este:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Quando o comando anterior for concluído e o aplicativo confiável tiver sido criado, execute Enable-CsTopology para garantir que as alterações entrem em vigor:

    Enable-CsTopology

Depois de executar o Enable-CsTopology, recomendamos reiniciar o computador.

Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configurando um certificado padrão no nó Inspetor

Cada nó do Inspetor deve ter um certificado padrão atribuído usando o assistente de implantação do Lync Server.

**Para atribuir um certificado padrão**

1.  Clique em **Iniciar**, em **todos os programas**, em **Lync Server**e em **Assistente de implantação do Lync Server**.

2.  No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server** e, em seguida, clique em **executar** sob a solicitação de título **, instalar ou atribuir certificado**.
    
    <div>
    

    > [!NOTE]
    > Se o botão <STRONG>executar</STRONG> estiver desabilitado, talvez seja necessário clicar primeiro em <STRONG>executar</STRONG> em <STRONG>instalar repositório de configuração local</STRONG>.

    
    </div>

3.  Siga um destes procedimentos:
    
      - Se você já tiver um certificado que pode ser usado como o certificado padrão, clique em **padrão** no assistente de certificado e clique em **atribuir**. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.
    
      - Se você precisar solicitar um certificado para usar o certificado padrão, clique em **solicitar** e siga as etapas no Assistente para solicitação de certificados para solicitar esse certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Instalando e configurando um nó de Inspetor

Depois de reiniciar o computador do nó do Inspetor e configurar um certificado, você precisará executar o arquivo Watchernode. msi. (Você deve executar o Watchernode. msi em um computador onde os arquivos de agente do Operations Manager e os componentes principais do Lync Server 2013 estejam instalados.)

**Para instalar e configurar um nó de Inspetor**

1.  Para abrir o Shell de gerenciamento do Lync Server, clique em **Iniciar**, em **todos os programas**, em **Lync Server**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (especificar o caminho real para a sua cópia do Watchernode. msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > Você também pode executar o Watchernode. msi a partir de uma janela de comando. Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de Comando</STRONG> e clique em <STRONG>Executar como administrador</STRONG>. Quando a janela de comando abrir, digite o mesmo comando anterior.

    
    </div>

Observe que o par nome/valor no comando anterior Authentication = TrustedServer diferencia maiúsculas de minúsculas. Você deve digitá-lo exatamente como mostrado. O comando a seguir falha porque não usa a capitalização de letras correta:

C:\\ferramentas\\Watchernode. msi Authentication = trustedserver

Você pode usar o modo TrustedServer somente com computadores localizados na rede de perímetro. Quando um nó do inspetor está em execução no modo TrustedServer, os administradores não precisam manter as senhas dos usuários do teste no computador.

</div>

</div>

<span> </span>

</div>

</div>

</div>

