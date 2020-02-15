---
title: Configurando um nó do inspetor para usar a autenticação de servidor confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba69980f97e901703f51f71729c661821e70e61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configurando um nó do Inspetor no Lync Server 2013 para usar a autenticação de servidor confiável

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Caso o seu computador de nó do inspetor estiver dentro da rede de perímetro, utilizar uma autenticação de Servidor Confiável pode reduzir drasticamente as taxas de administração para manter um único certificado em vez de diversas senhas de conta de usuário.

A primeira etapa na configuração da autenticação de Servidor Confiável é criar um pool de aplicativo confiável para hospedar o computador de nó do inspetor. Depois que o pool de aplicativo confiável tiver sido criado, você deverá então configurar transações sintéticas nos nós do inspetor para executar como um aplicativo confiável.

<div>


> [!NOTE]
> Um aplicativo confiável é um aplicativo que recebe status confiável para ser executado como parte do Lync Server 2013, mas que não é uma parte interna do produto. O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.



</div>

Para criar um pool de aplicativos confiáveis, abra o Shell de gerenciamento do Lync Server 2013 e execute um comando semelhante a este:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Para obter detalhes sobre os parâmetros usados no comando anterior, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

Após criar o pool de aplicativo confiável, configure o computador de nó do inspetor para executar transações sintéticas como aplicativo confiável. Isso é feito utilizando o cmdlet **New-CsTrustedApplication** e um comando similar a este:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Quando o comando estiver concluído e o aplicativo confiável for criado, execute Enable-CsTopology para certificar-se de que as alterações tenham efeito:

    Enable-CsTopology

Após executar o Enable-CsTopology, recomendamos que você reinicie o computador.

Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configurando um certificado padrão no nó do inspetor

Cada nó do Inspetor deve ter um certificado padrão atribuído usando o assistente de implantação do Lync Server.

**Para atribuir um certificado padrão**

1.  Clique em **Iniciar**, em **todos os programas**, em **Lync Server**e em **Assistente de implantação do Lync Server**.

2.  No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server** e clique em **executar** no cabeçalho **solicitar, instalar ou atribuir certificado**.
    
    <div>
    

    > [!NOTE]
    > Caso o botão <STRONG>Executar</STRONG> esteja inativo, talvez você precise clicar primeiro em <STRONG>Executar</STRONG>, sob <STRONG>Instalar Repositório de Configuração Local</STRONG>.

    
    </div>

3.  Faça um dos seguintes:
    
      - Se você já tiver um certificado que possa ser utilizado como certificado padrão, clique em **Padrão** no assistente de Certificado e, então, clique em **Atribuir**. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.
    
      - Se você precisar solicitar um certificado para utilizar o certificado padrão, clique em **Solicitar** e, então, siga as etapas no assistente de Solicitação de Certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Instalando e configurando um nó de inspetor

Depois de ter reiniciado o computador de nó do inspetor e configurado o certificado, você precisará executar o arquivo Watchernode.msi. (Você deve executar o Watchernode. msi em um computador onde os arquivos do agente do Operations Manager e os componentes principais do Lync Server 2013 estão instalados.)

**Para instalar e configurar um nó de inspetor**

1.  Abra o Shell de gerenciamento do Lync Server clicando em **Iniciar**, em **todos os programas**, em **Lync Server**e em **Shell de gerenciamento do Lync Server**.

2.  No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (especifique o caminho real para a sua cópia do Watchernode. msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > Você também pode executar o Watchernode.msi de uma janela de comando. Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de comando</STRONG> e, então, em <STRONG>Executar como administrador</STRONG>. Quando a janela de comando abrir, digite o mesmo comando anterior.

    
    </div>

Observe que o par de valor/nome no comando anterior Authentication=TrustedServer diferencia maiúscula de minúscula. Você deve digitar exatamente como mostrado. O comando a seguir falha porque não utiliza a formatação correta:

C:\\ferramentas\\Watchernode. msi Authentication = trustedserver

Você pode utilizar o modo TrustedServer apenas com computadores que estão localizados na rede do perímetro. Quando um nó de inspetor está executando no modo TrustedServer, os administradores não precisam manter senhas de usuário de teste no computador.

</div>

</div>

<span> </span>

</div>

</div>

</div>

