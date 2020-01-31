---
title: 'Lync Server 2013: gerenciamento de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb652485b03bcaee5e63bc4fc23d25fd5df958bd
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a>Gerenciamento de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-05-15_

Gerenciamento de configuração é o processo de gravação e acompanhamento de ativos de hardware e software e informações de configuração do sistema. Geralmente, é usado para acompanhar licenças de software, manter uma compilação de hardware e software padrão para computadores e servidores cliente e definir padrões de nomenclatura para novos computadores. O gerenciamento de configuração geralmente abrange as seguintes categorias:

  - **Hardware**   esta categoria controla os pedaços de equipamento que a organização de ti tem, onde o equipamento está localizado e quem usa equipamento. Essas informações permitem que uma organização planeje e planeje atualizações, mantenha compilações de hardware padrão, informe o valor dos ativos de ti para fins contábeis e ajude a evitar roubo.

  - **Software**   essa categoria controla o software instalado em cada computador, os números de versão e o local em que as licenças são mantidas. Essas informações ajudam a planejar atualizações, para garantir que o software seja licenciado e detectar a presença de softwares não autorizados (e não licenciados).

  - **Builds padrão esta**   categoria acompanha a compilação padrão atual para os computadores cliente e servidores e se os computadores cliente e servidores atendem a esse padrão. Definir e aplicar construções padrão ajuda a equipe de suporte porque a equipe é necessária para manter apenas um número limitado de versões de cada parte do software.

  - **Hotfixes e atualizações cumulativas**   essa categoria controla quais service packs são testados e aprovados para uso e quais computadores estão atualizados. Essas informações são importantes para reduzir o risco de que os computadores sejam comprometidos e para detectar os usuários que instalaram atualizações não aprovadas.

  - **Informações de configuração do sistema**   essa categoria acompanha a função de um sistema, a interação entre elementos do sistema e os processos que dependem de um sistema executando suavemente. Por exemplo, um servidor proxy de terceiros pode ser configurado em um único servidor. A dependência do servidor proxy neste servidor deve ser compreendida e os planos de contingência podem ser necessários se houver uma falha. Se o servidor proxy puder ser configurado para também se comunicar com outro servidor front-end, as dependências e os planos de contingência provavelmente serão alterados.

<div>

## <a name="implementing-configuration-management"></a>Implementando o gerenciamento de configuração

Depois de determinar quais itens precisam gerenciar, implemente o gerenciamento de configuração coletando dados e dados de relatório. A abordagem mais simples para pequenas organizações é coletar dados manualmente (número e modelo de computadores cliente, sistema operacional, software instalado) e salvá-los em um documento do Office Word ou Office Excel. Para sistemas maiores, mais complexos e em constante mudança, a descoberta de ativos e a coleta de informações detalhadas deve ser automatizada. Decidir quais informações são relevantes para a sua organização e gravá-las em um banco de dados.

O banco de dados de gerenciamento de configuração é uma ferramenta útil para a equipe de suporte e o gerenciamento nas seguintes áreas:

  - **Auditorias de segurança**   o banco de dados permite que você identifique os servidores que estão executando o Lync Server e sistemas de computador cliente que devem ter hotfixes aplicados ou que perderam a instalação de um Service Pack ou das atualizações mais recentes de antivírus.

  - **A instalação**   do software identificando versões do software cliente e controlando-as ajudará os administradores a planejar atualizações de versão e novas instalações e também ajudando com a documentação de licenciamento e a conformidade.

  - **Informações de configuração**   se você mantiver uma lista atualizada de todas as configurações que foram alteradas do padrão, você poderá solucionar problemas de forma rápida e eficiente.

  - **Planejando atualizações**   se uma avaliação de capacidade revelar que é necessário espaço de armazenamento adicional nos seus servidores de banco de dados do Lync, é importante saber se cada servidor tem um controlador RAID interno. Em caso afirmativo, eles são o mesmo modelo? Eles têm o mesmo número de discos instalados? O banco de dados de gerenciamento de configuração indicará o tipo de disco que pode ser instalado, o número e o caminho de atualização em cada caso.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Ferramentas usadas para gerenciamento de configuração

Há muitas ferramentas para detectar, auditar e relatar ativos. Algumas dessas ferramentas são discutidas nesta seção.

  - **Scripts automatizados**   você pode escrever scripts simples para relatar itens como o sistema operacional, o nível do Service Pack e se existe um software em um conjunto específico de computadores. Você pode escrever esses scripts para os requisitos exatos de uma organização. No entanto, o número necessário de scripts e sua complexidade pode fazer com que os scripts criem e mantenham seus custos caros.

  - **Ferramentas automatizadas**   dependendo do tamanho da sua empresa e de suas necessidades organizacionais, você pode querer considerar o uso de ferramentas automatizadas. Ferramentas como o Microsoft Endpoint Configuration Manager incorporam modelos de relatório padrão (como o nível de Service Pack) e também permitem que você crie relatórios personalizados, por exemplo, para um aplicativo personalizado. O Microsoft Endpoint Configuration Manager também pode ser usado para relatar configurações de hardware e software.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relação com gerenciamento de alterações

O gerenciamento de configuração está intimamente relacionado ao gerenciamento de alterações. O gerenciamento de configuração identifica a necessidade de alteração e identifica e registra a ocorrência de uma alteração. Por exemplo, o banco de dados de gerenciamento de configuração pode ser usado para identificar os servidores que exigem um hotfix. O gerenciamento de alterações define o processo para aplicar o hotfix.

Por outro lado, se uma nova atualização cumulativa for implementada, o processo de gerenciamento de alterações deverá fornecer essas informações para o sistema de gerenciamento de configuração. As ferramentas de gerenciamento de configuração provavelmente precisarão ser configuradas para identificar o novo software, para que eles possam descobrir e controlar onde e quando o software é implantado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

