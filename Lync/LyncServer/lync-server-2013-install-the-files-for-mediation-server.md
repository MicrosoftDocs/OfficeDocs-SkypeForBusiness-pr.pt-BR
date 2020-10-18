---
title: 'Lync Server 2013: instalar os arquivos para o servidor de mediação'
description: 'Lync Server 2013: instalar os arquivos do servidor de mediação.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574067"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Instalar os arquivos para o servidor de mediação no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-06_

Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.

Use as etapas deste tópico para executar o assistente de implantação do Lync Server 2013 para instalar os arquivos do servidor de mediação em um computador adicionado a um pool do servidor de mediação quando você usou o construtor de topologias para definir e publicar o pool. Ao instalar o servidor de mediação de arquivos, você também instala e atribui o certificado exigido por cada computador em um pool do servidor de mediação.

Neste site, se você já implantou servidores de mediação colocados no pool de front-ends ou no servidor Standard Edition, pode ignorar este tópico e, em vez disso, continuar a [Configurar troncos no Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Este tópico pressupõe que você já tenha definido e publicado um pool do servidor de mediação autônomo, conforme descrito em <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir um servidor de mediação no construtor de topologias no Lync Server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação de implantação e que você verificou que os computadores no pool do servidor de mediação atendem aos pré-requisitos descritos nos <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">pré-requisitos de software para o enterprise Voice no Lync Server 2013</A> e os <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">pré-requisitos de segurança e configuração para o Enterprise Voice no Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar os arquivos em um pool do Servidor de Mediação autônomo

1.  Na mídia de instalação, clique com o botão direito do mouse em \<installation media\> ** \\ Setup \\ AMD64 \\Setup.exe**e clique em **Executar como administrador**.

2.  Na página **Local de instalação**, clique em **OK**.

3.  Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)

4.  Na página **Assistente de Implantação do Lync Server 2010**, clique em **Instalar ou atualizar o sistema do Lync Server**.

5.  Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.

6.  Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.

7.  Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.

8.  Próximo a **Etapa 2: Configurar ou remover os componentes do Lync Server**, clique em **Executar** e em **Avançar**.

9.  Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.

10. Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribui-lo.

11. Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.

12. Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.

13. No computador em que você está executando o painel de controle do Lync Server, verifique na página **topologia** do painel de controle do Lync Server que o status do serviço do servidor de mediação é mostrado como uma marca de seleção verde. Se um X vermelho é exibido, selecione o Servidor de Mediação. No menu **Ações**, clique em **Iniciar todos os serviços**.

Se você tiver adicionado mais de um computador ao pool do servidor de mediação, execute as etapas neste procedimento em todos os outros computadores no pool do servidor de mediação. Se você não precisar instalar arquivos para o servidor de mediação para qualquer outro computador, siga os procedimentos em [Configurando troncos no Lync server 2013](lync-server-2013-configuring-trunks.md) para definir as configurações para a conexão de tronco entre este pool de servidor de mediação (ou todos os servidores de mediação em um site) e seu par.

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

