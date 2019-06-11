---
title: 'Lync Server 2013: instalar os arquivos do servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Instalar os arquivos do servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-06_

Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.

Use as etapas neste tópico para executar o assistente de implantação do Lync Server 2013 para instalar os arquivos do servidor de mediação em um computador que você adicionou a um pool do servidor de mediação quando usou o construtor de topologias para definir e publicar o pool. Ao instalar o servidor de mediação de arquivos, você também instala e atribui o certificado necessário para cada computador em um pool do servidor de mediação.

Neste site, se você já implantou servidores de mediação posicionados nos pools de front-end ou no servidor Standard Edition, você pode ignorar este tópico e, em vez disso, continuar a [Configurar troncos no Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Este tópico pressupõe que você já definiu e publicou um pool autônomo do servidor de mediação, conforme descrito em <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir um servidor de mediação no construtor de topologias no Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na implantação documentação e se você verificou que os computadores no pool do servidor de mediação atendem aos pré-requisitos descritos em <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">pré-requisitos de software para o Enterprise Voice no Lync Server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">pré-requisitos de segurança e configuração para Enterprise Voice no Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar os arquivos em um pool do Servidor de Mediação autônomo

1.  Na mídia de instalação, clique com o \<botão direito\>do mouse em instalação do**\\programa\\de instalação do\\AMD64. exe**e clique em **Executar como administrador**.

2.  Na página **Local de instalação**, clique em **OK**.

3.  Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)

4.  Na página do **Assistente de implantação do Lync Server 2010** , clique em **instalar ou atualizar o sistema do Lync Server**.

5.  Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.

6.  Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.

7.  Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.

8.  Ao lado da **etapa 2: configurar ou remover componentes do Lync Server**, clique em **executar**e, em seguida, clique em **Avançar**.

9.  Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.

10. Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribuí-lo.

11. Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.

12. Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.

13. No computador em que você está executando o painel de controle do Lync Server, verifique na página **Topology** do painel de controle do Lync Server que o status do serviço do servidor de mediação é mostrado como uma marca de seleção verde. Se um X vermelho é exibido, selecione o Servidor de Mediação. No menu **Ações**, clique em **Iniciar todos os serviços**.

Se você adicionou mais de um computador ao pool do servidor de mediação, execute as etapas neste procedimento em todos os outros computadores no pool do servidor de mediação. Se você não precisar instalar arquivos para o servidor de mediação para qualquer outro computador, siga os procedimentos em [Configurando troncos no Lync server 2013](lync-server-2013-configuring-trunks.md) para definir configurações para a conexão de tronco entre este pool de servidores de mediação (ou toda a mediação Servidores em um site) e seu par.

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

