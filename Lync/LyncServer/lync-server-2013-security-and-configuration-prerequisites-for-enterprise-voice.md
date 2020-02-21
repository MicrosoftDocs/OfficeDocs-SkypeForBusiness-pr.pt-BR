---
title: Pré-requisitos de segurança e configuração para o Enterprise Voice
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
ms.openlocfilehash: d8aec487e2ef5c6f5a756305a6e44df0c31cbec0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Pré-requisitos de segurança e configuração para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Verifique se a sua infraestrutura atende aos seguintes pré-requisitos de segurança, configuração do usuário e hardware específico ao cenário.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Direitos Administrativos e Infraestrutura do Certificado

Certifique-se que o ambiente está configurado com os grupos de usuários administrativos e infraestrutura de certificado para o uso durante o processo de implantação do Enterprise Voice.

  - Os administradores responsáveis pela implantação do Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.

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
    > Para obter detalhes sobre os requisitos de certificado no Lync Server, consulte <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate Infrastructure Requirements for Lync server 2013</A> na documentação de planejamento.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configuração do usuário

Se você colocar o servidor de mediação com cada pool de front-ends ou servidor Standard Edition durante a implantação de front end, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.

Se você estiver recém implantando a carga de trabalho do Enterprise Voice, antes de iniciar o processo de implantação, designe um número de telefone principal para cada usuário que você planeja habilitar para o Enterprise Voice. Como administrador, você é responsável por certificar-se que esse número seja exclusivo. Antes da implementação, todos os números de telefone principais devem ser normalizados (formatados corretamente) e copiados para a propriedade **URI de linha** de cada usuário usando o painel de controle do Lync Server.

<div>


> [!NOTE]
> Para obter exemplos de números de telefone principais necessários para a implantação do Enterprise Voice, consulte a seção <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync server 2013</A> de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync Server 2013</A> na documentação de planejamento.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Próximas etapas: Instalar arquivos ou configurar a conectividade da PSTN

Depois de verificar os pré-requisitos de software e de ambiente para o Enterprise Voice, você pode usar o conteúdo a seguir para:

  - Instale o servidor de mediação, conforme descrito em [install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mas somente se você deseja implantar um servidor de mediação autônomo ou pool porque os servidores de mediação são instalados como parte do processo de implantação do servidor de front-end ou Standard Edition quando colocado.

  - Ou, comece a definir as configurações para rotear chamadas para usuários do Enterprise Voice, conforme descrito em [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

