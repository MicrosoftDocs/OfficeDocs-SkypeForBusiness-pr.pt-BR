---
title: 'Lync Server 2013: gerenciamento de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507828"
---
# <a name="configuration-management-in-lync-server-2013"></a>Gerenciamento de configuração no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-05-15_

O gerenciamento de configuração é o processo de gravação e acompanhamento de ativos de hardware e software e informações de configuração do sistema. Geralmente, é usado para controlar licenças de software, manter uma compilação de hardware e software padrão para computadores clientes e servidores e definir padrões de nomenclatura para novos computadores. O gerenciamento de configuração geralmente abrange as seguintes categorias:

  - **Hardware**     Esta categoria acompanha as partes de equipamento que a organização de ti possui, onde o equipamento está localizado e quem usa equipamento. Essas informações permitem que uma organização planeje e orçasse atualizações, mantenha compilações de hardware padrão, informe o valor dos ativos de ti para fins contábeis e ajude a evitar o roubo.

  - **Software**     Esta categoria acompanha o software instalado em cada computador, os números de versão e onde as licenças são mantidas. Essas informações ajudam a planejar atualizações, para garantir que o software seja licenciado e a detectar a presença de softwares não autorizados (e não licenciados).

  - **Compilações padrão**     Esta categoria acompanha a compilação padrão atual para os computadores clientes e servidores e se os computadores clientes e servidores atendem a esse padrão. A definição e a aplicação de compilações padrão ajuda a equipe de suporte porque a equipe precisa manter apenas um número limitado de versões de cada parte do software.

  - Hotfixes e atualizações **cumulativas**     Esta categoria acompanha quais service packs são testados e aprovados para uso e quais computadores estão atualizados. Essas informações são importantes para reduzir o risco de que os computadores sejam comprometidos e para detectar usuários que instalaram atualizações não aprovadas.

  - Informações de configuração do **sistema**     Essa categoria acompanha a função de um sistema, a interação entre elementos do sistema e os processos que dependem de um sistema que está funcionando sem problemas. Por exemplo, um servidor proxy de terceiros pode ser configurado em um único servidor. A dependência do servidor proxy neste servidor deve ser compreendida e os planos de contingência podem ser necessários se houver uma falha. Se o servidor proxy puder ser configurado para se comunicar também com outro servidor front-end, as dependências e os planos de contingência provavelmente serão alterados.

<div>

## <a name="implementing-configuration-management"></a>Implementar o gerenciamento de configuração

Depois de determinar quais itens precisam de gerenciamento, implemente o gerenciamento de configuração coletando dados e dados de relatórios. A abordagem mais simples para pequenas organizações é coletar dados manualmente (número e modelo de computadores cliente, sistema operacional, software instalado) e salvá-los em um documento do Office Word ou Office Excel. Para sistemas maiores, mais complexos e em constante mudança, a descoberta de ativos e coleção de informações detalhadas deve ser automatizada. Decidir quais informações são relevantes para a sua organização e gravá-las em um banco de dados.

O banco de dados de gerenciamento de configuração é uma ferramenta útil para o gerenciamento e equipe de suporte nas seguintes áreas:

  - **Auditorias**     de segurança O banco de dados permite que você identifique servidores que estão executando o Lync Server e sistemas de computador cliente que precisam ter hotfixes aplicados ou que perderam a instalação de um Service Pack ou as atualizações mais recentes de antivírus.

  - **Instalação**     de software A identificação de versões de software cliente e o acompanhamento delas ajudarão os administradores a planejar atualizações de versão e novas instalações e também ajudando a documentação e conformidade de licenciamento.

  - **Informações**     de configuração Se você mantiver uma lista atualizada de todas as configurações que foram alteradas de seu padrão, poderá solucionar problemas com rapidez e eficácia.

  - **Planejamento de atualizações**     Se uma revisão de capacidade revelar que é necessário espaço de armazenamento adicional nos servidores de banco de dados do Lync, é importante saber se cada servidor tem um controlador RAID interno. Se o fizerem, então eles serão o mesmo modelo? Eles têm o mesmo número de discos instalados? O banco de dados de gerenciamento de configuração indicará o tipo de disco que pode ser instalado, o número e o caminho de atualização em cada caso.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Ferramentas usadas para o gerenciamento de configuração

Há muitas ferramentas para descobrir, auditar e relatar ativos. Algumas dessas ferramentas são discutidas nesta seção.

  - **Scripts**     automatizados Você pode escrever scripts simples para relatar itens como o sistema operacional, o nível de Service Pack e se o software existe em um conjunto específico de computadores. Você pode escrever esses scripts para os requisitos exatos de uma organização. No entanto, o número necessário de scripts e sua complexidade pode tornar os scripts caros de criar e manter.

  - **Ferramentas**     automatizadas Dependendo do tamanho da sua empresa e das suas necessidades organizacionais, convém considerar o uso de ferramentas automatizadas. Ferramentas como o Microsoft Endpoint Configuration Manager incorporam modelos de relatório padrão (como o nível de pacote de serviço) e também permitem que você crie relatórios personalizados, por exemplo, para um aplicativo personalizado. O Microsoft Endpoint Configuration Manager também pode ser usado para relatar configurações de hardware e de software.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relação com o gerenciamento de alterações

O gerenciamento de configuração está intimamente relacionado ao gerenciamento de alterações. O gerenciamento de configuração identifica a necessidade de alteração e identifica e registra que uma alteração ocorreu. Por exemplo, o banco de dados de gerenciamento de configuração pode ser usado para identificar servidores que exigem um hotfix. O gerenciamento de alterações define o processo de aplicação do hotfix.

Por outro lado, se uma nova atualização cumulativa for distribuída, o processo de gerenciamento de alterações deverá fornecer essas informações ao sistema de gerenciamento de configuração. As ferramentas de gerenciamento de configuração provavelmente precisarão ser configuradas para identificar o novo software, para que eles possam descobrir e controlar onde e quando o software é implantado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

