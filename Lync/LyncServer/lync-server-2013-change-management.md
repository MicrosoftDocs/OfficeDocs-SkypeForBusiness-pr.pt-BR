---
title: 'Lync Server 2013: gerenciamento de alterações'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13eb521ea6b4be5f8d701885df65a3e1672b2eaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Gerenciamento de alterações no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-18_

As alterações no ambiente de ti são inevitáveis. As alterações incluem novas tecnologias, sistemas, aplicativos, hardware, ferramentas, processos e alterações em funções e responsabilidades. Um sistema de gerenciamento de alterações eficaz permite introduzir mudanças no ambiente de ti rapidamente e com interrupção mínima do serviço. Um sistema de gerenciamento de alterações reúne as equipes envolvidas na alteração de um sistema. Por exemplo, decidir tirar proveito dos Office Web Apps. Esse é um aplicativo de serviço do Lync integrado que permite aos usuários ler e editar documentos em um navegador. A implementação desse serviço, após você ter entrado em produção, requer o envolvimento de várias equipes:

  - **Equipe de teste**   esta carga da equipe-testa os aplicativos Web do Office em um servidor de teste, no processo que fornece informações sobre os padrões de uso esperados e o desempenho esperado dos servidores de produção.

  - **Administradores do Lync**   essa equipe determina a estratégia de implantação e os scripts que a instalação foi possível. A equipe é responsável por verificar se a alteração foi implantada no ambiente de produção e se é responsável por administração posteriormente. A equipe deve entender o efeito das alterações e incorporá-las nos procedimentos antes que as alterações sejam colocadas em produção

  - **Equipe de rede**   esta equipe é responsável por alterações nas regras de firewall que permitem o acesso da Internet aos servidores do pool interno do Lync. A equipe também é responsável por trabalhar com os administradores do Lync para garantir que a largura de banda disponível possa dar suporte à carga adicional.

  - **Equipe de segurança**   esta equipe avalia a segurança e minimiza os riscos. A equipe de segurança deve revisar as vulnerabilidades conhecidas e ajudar a garantir que os riscos de segurança sejam minimizados.

  - **Equipe de aceitação do usuário**   essa equipe é composta de usuários que estão dispostos a testar o sistema e oferecer comentários para melhorias.

O processo de gerenciamento de alterações define as responsabilidades de cada equipe e agenda o trabalho a ser realizado, a incorporação de verificações e testes onde elas são necessárias. Os controles de alteração irão variar dependendo da complexidade e do efeito esperado de uma alteração. Elas podem variar de acordo com a aprovação automática das alterações, para alterar reuniões de revisão até análises completas no nível do projeto. Para explicar isso melhor, os grupos de alterações são discutidos nesta seção.

  - **Alterações principais alterações**   importantes têm um efeito global no sistema e podem exigir entrada de várias equipes. Um exemplo disso é a atualização para o Lync Server 2013. Alterações importantes afetam muitas equipes e, talvez, sistemas diferentes. O processo de gerenciamento de alterações provavelmente incluirá uma ou mais reuniões de revisão de alterações para informar as equipes que serão envolvidas na alteração ou que serão afetadas pela alteração.

  - **Alterações significativas alterações**   significativas exigem recursos significativos para planejar, criar e implementar. Os controles de alteração apropriados devem ser introduzidos para ajudar a garantir que o efeito da alteração seja entendido, que os procedimentos de implantação sejam testados e que os planos de reversão e contingência estejam prontos. Um exemplo de uma alteração significativa é implantar uma nova atualização cumulativa.

  - ****   Alterações secundárias pequenas alterações não afetam significativamente o ambiente de ti, por exemplo, alterar determinadas políticas do Lync por meio do painel de controle do Microsoft Lync Server 2013.

  - **Alterações padrão as**   alterações padrão são executadas regularmente e são bem compreendidas e documentadas. O processo de gerenciamento de alterações deve revisar todas as alterações nos procedimentos. Ele não deve ser necessário para mudanças de rotina, como criar um banco de dados de conteúdo ou adicionar um usuário.

O exemplo a seguir de gerenciamento de alterações examina como as diferentes equipes interagem e as ações que são executadas quando um novo Service Pack é implantado. Essas ações são organizadas e gerenciadas pelo processo de gerenciamento de alterações.

  - **Gerar uma solicitação**   de alteração a equipe de segurança avaliou o Service Pack mais recente e confirmou que ele resolve uma possível vulnerabilidade no sistema de produção. A equipe eleva uma solicitação de alteração para ter a nova atualização cumulativa aplicada a todos os servidores que executam o Lync Server.

  - **Notas de versão do Service Pack**   revisar a equipe do administrador do Lync revisa as notas de versão do Service Pack para identificar o efeito no sistema.

  - **Uma série de testes de laboratório é realizada**   a equipe do administrador do Lync deve executar atualizações de teste em um servidor em um ambiente de teste para decidir se o Service Pack pode ser aplicado com êxito sem afetar qualquer um dos aplicativos e servidor instalados os. Se houver aplicativos de terceiros ou criados internamente que fazem interface com o Lync Server em um ambiente de produção, eles também deverão ser testados. Esses testes também podem ser usados para estimar o tempo necessário para executar as atualizações.

  - **Os usuários são informados sobre a interrupção**   que a equipe do administrador do Lync, a equipe de comunicações ou o suporte técnico do usuário informa todos os usuários afetados sobre o ciclo de manutenção planejado e por quanto tempo o serviço estará indisponível.

  - **Um backup completo do Lync é executado antes da atualização**   que a equipe do administrador do Lync deve verificar se há um backup válido que pode ser usado para reverter para o estado do sistema original, caso a instalação do Service Pack falhe. Recomendamos que o backup seja restaurado para um servidor em standby para que esse sistema seja imediatamente disponibilizado se houver problemas.

  - **A atualização cumulativa é**   implantada a equipe do administrador do Lync faz a instalação durante o ciclo de manutenção planejado.

<div>

## <a name="managing-the-timing-of-changes"></a>Gerenciando o intervalo de alterações

Recomendamos que você implemente um procedimento para agendar alterações para evitar interrupções em seções sobrepostas do seu trabalho. Por exemplo, duas equipes podem estar planejando uma pequena alteração para um sistema. Uma equipe pode estar aplicando uma atualização cumulativa em um pool enquanto outra equipe está migrando os usuários herdados para esse pool. Nenhuma equipe é afetada pelas alterações que a outra equipe está planejando, e cada equipe pode não necessariamente saber sobre alterações que a outra equipe está planejando. Se ambas as alterações ocorrerem ao mesmo tempo, pode haver problemas para implementar as alterações. Além disso, se houver problemas após a aplicação das alterações, por exemplo, se a migração do usuário falhar, pode ser difícil decidir qual alteração deve ser revertida. Deve haver períodos de manutenção regulares configurados entre ti e gerenciamento para testar as alterações e aceitá-las.

</div>

</div>

<span> </span>

</div>

</div>

</div>

