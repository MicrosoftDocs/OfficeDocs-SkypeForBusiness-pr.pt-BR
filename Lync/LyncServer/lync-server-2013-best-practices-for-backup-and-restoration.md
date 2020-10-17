---
title: 'Lync Server 2013: práticas recomendadas para backup e restauração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca14913d063a8691d0477af912e70e72b91143fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535198"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Práticas recomendadas para backup e restauração do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Esta seção inclui dois tipos de melhores práticas:

  - Práticas recomendadas para backup e restauração.

  - Práticas recomendadas para minimizar o impacto de um desastre.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Melhores práticas para backup e restauração

Para facilitar o processo de backup e restauração, aplique as seguintes práticas recomendadas ao fazer backup ou restaurar seus dados:

  - Execute backups regulares a intervalos adequados. O tipo de backup e agendamento rotativo mais simples e mais comumente usado é o backup noturno completo de todo o banco de dados SQL Server. Em seguida, se a restauração for necessária, o processo de restauração exigirá apenas um backup, e não mais do que os dados de um dia devem ser perdidos.

  - Se você usar cmdlets ou o painel de controle do Lync Server para fazer alterações de configuração, use o cmdlet **Export-CsConfiguration** para fazer um backup de instantâneo do arquivo de configuração de topologia (XDS. MDF) após fazer as alterações, para que você não perca as alterações se precisar restaurar os bancos de dados. Observe que essa configuração é submetida a backup no formato XML e compactada como um arquivo ZIP.

  - Certifique-se de que a pasta compartilhada que você planeja usar para fazer backup do Lync Server tem espaço em disco suficiente para armazenar todos os dados de backup.

  - Agendar backups quando o uso do Lync Server costuma ser baixo, para melhorar o desempenho do servidor e a experiência do usuário.

  - Certifique-se de que o local onde você faz backup dos dados é seguro (recomendamos um local remoto).

  - Mantenha os arquivos de backup onde eles estarão disponíveis, caso você precise restaurar os dados.

  - Planejar e agendar testes periódicos dos processos de restauração suportados pela sua organização.

  - Valide seus processos de backup e restauração com antecedência para garantir que eles funcionem conforme o esperado.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Melhores práticas para minimizar o impacto de um desastre

A melhor estratégia para lidar com interrupções de serviço desastrosas (causadas por eventos não gerenciáveis, como quedas de energia ou falhas repentinas de hardware) é supor que eles ocorram e planejar de acordo.

Se os serviços do Lync, com um mínimo de interrupções e paralisações, forem críticos para os negócios de sua organização, você deverá considerar a implementação de pools de front-end em pares, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Em seguida, se um desses pools tiver um desastre, um administrador pode mudar os usuários desse pool para serem servidos pelo outro pool, com um mínimo de tempo de inatividade.

Os planos de gerenciamento de desastres desenvolvidas como parte da estratégia de backup e restauração devem incluir o seguinte:

  - Manter a mídia de software e as atualizações de software e firmware prontamente disponíveis.

  - Manter registros de hardware e software.

  - Fazer o backup de seus dados regularmente e monitorar a integridade dos backups.

  - Treinar sua equipe em recuperação de desastres, procedimentos de documentação e implementar exercícios de simulação de recuperação de desastres.

  - Manter o hardware de reserva disponível ou, se você tiver um contrato de nível de serviço (SLA), contratando com fornecedores de hardware e fornecedores para substituição de prompts.

  - Separar a localização dos seus arquivos de log de transações (arquivos .ldf) e arquivos de banco de dados (arquivos .mdf).

</div>

</div>

<span> </span>

</div>

</div>

</div>

