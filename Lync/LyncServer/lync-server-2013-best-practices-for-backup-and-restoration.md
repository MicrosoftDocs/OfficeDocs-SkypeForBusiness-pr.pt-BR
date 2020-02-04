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
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Práticas recomendadas para backup e restauração do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Esta seção inclui dois tipos de práticas recomendadas:

  - Práticas recomendadas para backup e restauração.

  - Práticas recomendadas para minimizar o impacto de um desastre.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Práticas recomendadas para backup e restauração

Para facilitar o processo de backup e restauração, aplique as seguintes práticas recomendadas ao fazer backup ou restaurar seus dados:

  - Faça backups regulares em intervalos apropriados. O tipo de backup mais simples e mais comumente usado e o cronograma de rotação é um backup noturno completo de todo o banco de dados SQL Server. Em seguida, se a restauração for necessária, o processo de restauração exigirá apenas um backup, e não mais do que os dados do dia deverão ser perdidos.

  - Se você usar cmdlets ou o painel de controle do Lync Server para fazer alterações de configuração, use o cmdlet **Export-CsConfiguration** para fazer um backup de instantâneo do arquivo de configuração de topologia (XDS. MDF) depois de fazer as alterações, para que você não perca as alterações se precisar restaurar seus bancos de dados. Observe que a configuração é feita com o backup em formato XML e compactada como um arquivo ZIP.

  - Verifique se a pasta compartilhada que você planeja usar para fazer backup do Lync Server tem espaço em disco suficiente para armazenar todos os dados de backup.

  - Agende backups quando o uso do Lync Server geralmente está baixo, para melhorar o desempenho do servidor e a experiência do usuário.

  - Verifique se o local onde você fez backup dos dados é seguro (recomendamos um local remoto).

  - Mantenha os arquivos de backup onde estarão disponíveis, caso você precise restaurar os dados.

  - Planeje e agende testes periódicos dos processos de restauração que têm suporte na sua organização.

  - Valide seus processos de backup e restauração com antecedência para garantir que eles funcionem conforme o esperado.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Práticas recomendadas para minimizar o impacto de um desastre

A melhor estratégia para lidar com interrupções de serviço desastrosas (causados por eventos não gerenciáveis, como quedas de energia ou falhas súbitas de hardware) é pressupor que elas ocorram e planejar de acordo com isso.

Se os serviços do Lync, com um mínimo de interrupções e paralisações, forem críticos para a sua organização, você deve considerar a implementação de pools de front-ends em pares, conforme descrito em [planejamento para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Em seguida, se um desses pools tiver um desastre, um administrador poderá trocar os usuários desse pool a serem servidos pelo outro pool, com um mínimo de tempo de inatividade.

Os planos de gerenciamento de desastres desenvolvidos como parte da estratégia de backup e restauração devem incluir o seguinte:

  - Manter a mídia do software e as atualizações de software e firmware prontamente disponíveis.

  - Manutenção de registros de hardware e software.

  - Fazer backup de seus dados regularmente e monitorar a integridade dos backups.

  - Treinar seus funcionários em recuperação de desastres, documentar procedimentos e fazer a implementação de buscas de simulação de recuperação de desastres.

  - Manter o hardware de reserva disponível ou, se você tiver um contrato de nível de serviço (SLA), contratar fornecedores e fornecedores de hardware para fazer substituições de solicitações.

  - Separar o local dos arquivos de log de transação (arquivos. ldf) e arquivos de banco de dados (arquivos. MDF).

</div>

</div>

<span> </span>

</div>

</div>

</div>

