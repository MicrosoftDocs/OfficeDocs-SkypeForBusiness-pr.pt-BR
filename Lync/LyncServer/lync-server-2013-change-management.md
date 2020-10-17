---
title: 'Lync Server 2013: gerenciamento de alterações'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2207dc527f73393c867f1aced8c8fceb2c4c6941
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517838"
---
# <a name="change-management-in-lync-server-2013"></a>Gerenciamento de alterações no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-18_

As alterações no ambiente de ti são desevitadas. As alterações incluem novas tecnologias, sistemas, aplicativos, hardware, ferramentas, processos e alterações em funções e responsabilidades. Um sistema eficaz de gerenciamento de alterações permite introduzir alterações no ambiente de ti rapidamente e com interrupção mínima do serviço. Um sistema de gerenciamento de alterações reúne as equipes envolvidas na alteração de um sistema. Por exemplo, a decisão de aproveitar o Office Web Apps. Este é um aplicativo de serviço do Lync integrado que permite que os usuários leiam e editem documentos em um navegador. A implementação desse serviço, depois que você tiver entrado em produção, requer o envolvimento de várias equipes:

  - **Equipe**     de teste Esta equipe realiza testes de carga do Office Web Apps em um servidor de teste, no processo que fornece informações sobre os padrões de uso esperados e o desempenho esperado dos servidores de produção.

  - **Administradores**     do Lync Essa equipe determina a estratégia de implantação e os scripts que a instalação era possível. A equipe é responsável por garantir que a alteração seja implantada no ambiente de produção e seja responsável pela administração posteriormente. A equipe deve entender o efeito das alterações e incorporá-las aos procedimentos antes que as alterações sejam colocadas em produção

  - **Equipe**     de rede Essa equipe é responsável por alterações nas regras de firewall que permitem o acesso da Internet aos servidores internos do pool do Lync. A equipe também é responsável por trabalhar com os administradores do Lync para garantir que a largura de banda disponível possa oferecer suporte à carga adicional.

  - **Equipe**     de segurança Essa equipe avalia a segurança e minimiza os riscos. A equipe de segurança deve revisar vulnerabilidades conhecidas e ajudar a garantir que os riscos de segurança sejam minimizados.

  - Equipe de aceitação do **usuário**     Essa equipe é composta de usuários que desejam testar o sistema e oferecer comentários sobre melhorias.

O processo de gerenciamento de alterações define as responsabilidades de cada equipe e agenda o trabalho a ser executado, incorporando verificações e testes onde eles são necessários. Os controles de alteração irão variar dependendo da complexidade e do efeito esperado de uma alteração. Eles podem variar de acordo com a aprovação automática de pequenas alterações, para alterar as reuniões de revisão, para revisões completas no nível do projeto. Para explicar isso melhor, os grupos de alterações são discutidos nesta seção.

  - **Alterações principais**     As principais alterações têm um efeito global no sistema e podem exigir entradas de várias equipes. Um exemplo disso é a atualização para o Lync Server 2013. Alterações principais afetam muitas equipes e, talvez, sistemas diferentes. O processo de gerenciamento de alterações provavelmente incluirá uma ou mais reuniões de revisão de alteração para informar as equipes que serão envolvidas na alteração ou que serão afetadas pela alteração.

  - **Alterações significativas**     Alterações significativas exigem recursos significativos para planejar, criar e implementar. Os controles de alteração apropriados devem ser introduzidos para ajudar a garantir que o efeito da alteração seja compreendido, que os procedimentos de implantação sejam testados e que os planos de reversão e contingência estejam prontos. Um exemplo de uma alteração significativa é a implantação de uma nova atualização cumulativa.

  - **Alterações**     secundárias Alterações secundárias não afetam significativamente o ambiente de ti, por exemplo, alterando determinadas políticas do Lync por meio do painel de controle do Microsoft Lync Server 2013.

  - **Alterações padrão**     As alterações padrão são realizadas regularmente e são bem compreendidas e documentadas. O processo de gerenciamento de alterações deve revisar todas as alterações nos procedimentos. Ele não deve ser necessário para alterações rotineiras, como criar um banco de dados de conteúdo ou adicionar um usuário.

O exemplo a seguir do gerenciamento de alterações examina como as diferentes equipes interagem e as ações que são executadas quando um novo Service Pack é implantado. Essas ações são organizadas e gerenciadas pelo processo de gerenciamento de alterações.

  - **Gerar uma solicitação**     de alteração A equipe de segurança avaliou o Service Pack mais recente e confirmou que ele resolve uma possível vulnerabilidade no sistema de produção. A equipe levanta uma solicitação de alteração para que a nova atualização cumulativa seja aplicada a todos os servidores que executam o Lync Server.

  - Análise das notas de **versão do Service Pack**     A equipe do administrador do Lync revisa as notas de versão do Service Pack para identificar o efeito no sistema.

  - **Uma série de testes de laboratório é realizada**     A equipe do administrador do Lync deve realizar atualizações de teste em um servidor em um ambiente de teste para decidir se o Service Pack pode ser aplicado com êxito sem afetar nenhum dos aplicativos e sistemas de servidor instalados. Se houver aplicativos de terceiros ou criados internamente que fazem interface com o Lync Server em um ambiente de produção, eles também devem ser testados. Esses testes também podem ser usados para estimar o tempo necessário para executar as atualizações.

  - **Os usuários são informados sobre a interrupção**     A equipe do administrador do Lync, a equipe de comunicações ou o suporte técnico do usuário informa todos os usuários afetados sobre o ciclo de manutenção planejado e quanto tempo o serviço estará indisponível.

  - **Um backup completo do Lync é executado antes da atualização**     A equipe de administrador do Lync deve verificar se há um backup válido que pode ser usado para reverter para o estado do sistema original se a instalação do Service Pack falhar. Recomendamos que o backup seja restaurado para um servidor em espera para que esse sistema fique disponível imediatamente se houver problemas.

  - **A atualização cumulativa está implantada**     A equipe do administrador do Lync faz a instalação durante o ciclo de manutenção planejado.

<div>

## <a name="managing-the-timing-of-changes"></a>Gerenciando o tempo das alterações

Recomendamos que você implemente um procedimento para agendar alterações para evitar interrupções em seções sobrepostas de seu trabalho. Por exemplo, duas equipes podem estar planejando uma pequena alteração para um sistema. Uma equipe pode estar aplicando uma atualização cumulativa em um pool enquanto outra equipe estiver migrando usuários herdados para esse pool. Nenhuma equipe é afetada pelas alterações que a outra equipe está planejando, e cada equipe pode não conhecer necessariamente as alterações que a outra equipe está planejando. Se as duas alterações ocorrerem ao mesmo tempo, pode haver problemas para implementar as alterações. Além disso, se houver problemas depois que as alterações forem aplicadas, por exemplo, se a migração do usuário falhar, talvez seja difícil decidir qual alteração deve ser revertida. Deve haver períodos regulares de manutenção configurados entre ti e gerenciamento para testar as alterações e aceitá-las.

</div>

</div>

<span> </span>

</div>

</div>

</div>

