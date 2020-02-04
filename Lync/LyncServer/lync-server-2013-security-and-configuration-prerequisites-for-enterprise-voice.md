---
title: Pré-requisitos de configuração e segurança para Entreprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Pré-requisitos de configuração e segurança para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Verifique se a sua infraestrutura atende às seguintes configurações de segurança, configuração do usuário e de hardware específicas do cenário.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Direitos administrativos e infraestrutura de certificado

Certifique-se de que seu ambiente esteja configurado com os seguintes grupos de usuários administrativos e infraestrutura de certificado para uso durante o processo de implantação do Enterprise Voice.

  - Os administradores que implantam o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.

  - Administradores realizando as tarefas de configuração devem ter direitos adequados:
    
      - **CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.
    
      - **CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.
    
      - **CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > A delegação permite que mais administradores participem da sua implantação do Lync Server sem abrir o acesso desnecessário aos recursos.

    
    </div>

  - A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes sobre os requisitos de certificado no Lync Server, consulte <A href="lync-server-2013-certificate-infrastructure-requirements.md">requisitos de infraestrutura de certificado para o Lync Server 2013</A> na documentação de planejamento.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configuração do usuário

Se você colocar o servidor de mediação em cada pool de front-end ou servidor Standard Edition durante a implantação de front-end, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.

Se você estiver implantando a carga de trabalho de Enterprise Voice no momento, antes de começar o processo de implantação, designe um número de telefone principal para cada usuário que você planeja habilitar para o Enterprise Voice. Como administrador, você é responsável por certificar-se que esse número seja exclusivo. Antes da implementação, todos os números de telefone primários devem ser normalizados (formatados corretamente) e copiados para cada propriedade de **URI de linha** do usuário usando o painel de controle do Lync Server.

<div>


> [!NOTE]
> Para obter exemplos de números de telefone primários necessários para a implantação do Enterprise Voice, consulte a seção <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync server 2013</A> de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync Server 2013</A> na documentação de planejamento.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Próximas etapas: instalar arquivos ou configurar a conectividade PSTN

Depois de verificar o software e os pré-requisitos ambientais para o Enterprise Voice, você pode usar o seguinte conteúdo para:

  - Instale o servidor de mediação, conforme descrito em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mas somente se você quiser implantar um servidor ou pool autônomo de mediação, pois os servidores de mediação são instalados como parte do processo de implantação do servidor do front-end ou da edição padrão quando posicionado.

  - Ou comece a definir as configurações para direcionar as chamadas para usuários do Enterprise Voice, conforme descrito em [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

