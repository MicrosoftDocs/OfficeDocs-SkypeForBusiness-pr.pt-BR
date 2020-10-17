---
title: 'Lync Server 2013: considerações de migração para reuniões'
description: 'Lync Server 2013: considerações de migração para reuniões.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e238405acf7bc2a96fd2efd4cca761c1f1f258fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560937"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Considerações de migração para reuniões no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-10_

Os seguintes tópicos são discutidos nesta seção:

  - Alterações em reuniões no Microsoft Lync Server 2013

  - Migrando usuários com base em suas necessidades de conferência

  - Migrando reuniões existentes e conteúdo da reunião

  - Experiência do usuário durante a migração do Lync Server 2010

  - Experiência do usuário durante a migração do Office Communications Server 2007 R2

  - Compatibilidade do Microsoft Lync 2013 com reuniões em versões anteriores do servidor

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Alterações em reuniões no Lync Server 2013

**Recursos do Lync Server 2013.**     O Lync Server 2013 fornece novos recursos de conferência que ficam disponíveis para os usuários depois que suas contas são movidas para o Lync Server 2013 e entram no cliente Lync 2013. Novos recursos são descritos em [novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [novidades para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL da reunião.**     Como no Lync Server 2010, todas as reuniões recentemente agendadas no Lync Server 2013 têm um prefixo de URL de https://e as reuniões existentes migram junto com as contas de usuário. No entanto, o Lync Server 2013 não dá suporte à chamada de conferência do Office Communications Server 2007 R2 (prefixo de URL conf://) ou à Web Conference (prefixo de URL meet://). Consulte "migrando reuniões do Office Communications Server 2007 R2", mais adiante neste tópico para obter mais informações.

**Suporte ao cliente.**     Ao contrário do Lync Server 2010, o Lync Server 2013 não é compatível com clientes do Office Communicator para conferência. Não é possível usar os seguintes clientes para participar de reuniões agendadas por meio do suplemento de reunião online do Lync 2013:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante a migração, os usuários do Office Communicator 2007 R2 devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013 até que os clientes sejam atualizados. Observe que os usuários do Office Communicator 2007 R2 podem continuar a usar o cliente existente no Lync Server 2013 para recursos de presença e IM, mas os recursos de conferência não são suportados.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrando usuários com base em suas necessidades de conferência

**Organizadores de reuniões frequentes.**     Considere migrar organizadores de reunião freqüentes no início do processo para que eles possam aproveitar os novos recursos do Lync Server 2013 e do Lync 2013 descritos em [novos recursos de conferência no Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novidades para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Usuários do Live Meeting.**     Se você estiver migrando do Office Communications Server 2007 R2 e tiver usuários que precisam de recursos de Webconferência específicos para o Live Meeting, particularmente o suporte para grandes reuniões e salas de desativação — você tem as seguintes opções:

  - Aconselhar os organizadores a usarem o serviço do Live Meeting, se disponível na sua organização.

  - Deixe os organizadores hospedados na versão anterior do Office Communications Server, para que eles possam continuar a agendar conferências da Web do Live Meeting com base no servidor.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrando reuniões existentes e conteúdo da reunião

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrando reuniões do Lync Server 2010

Quando você move um usuário do Lync Server 2010 para o Lync Server 2013, as seguintes informações são movidas com a conta do usuário:

  - Reuniões já programadas pelo usuário. Isso inclui diretórios de conferência e dados de conferência.

  - O número de identificação pessoal (PIN) do usuário. O PIN atual do usuário continua a funcionar até vencer ou o usuário solicitar um novo PIN.

No entanto, as seguintes informações da conta de usuário não são movidas para o novo servidor:

  - Conteúdo de reunião, por exemplo, apresentações do PowerPoint, conteúdo do quadro de comunicações e dados de pesquisa

Para mover o conteúdo que foi compartilhado em reuniões, use o parâmetro MoveMeetingContent do cmdlet Move-CsUser. Para obter detalhes sobre como usar esse cmdlet, consulte [move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) na documentação de cmdlets do Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrando reuniões do Office Communications Server 2007 R2

As reuniões do Office Communications Server 2007 R2 são chamadas de conferência (prefixo de URL conf://) ou webconferências (prefixo de URL meet://). O Lync Server 2013 não é compatível com as conferências anteriores do conf://e do meet://e não são migrados junto com a conta do usuário. Após a migração, você deve instruir os usuários a atualizar os links para todas as reuniões online que eles agendaram. Eles podem fazer isso após a instalação do cliente Lync 2013 abrindo um convite de reunião agendada, que atualiza a URL da reunião, e reenvia o convite aos participantes.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Experiência do usuário durante a migração do Lync Server 2010

Esta seção fornece um resumo da experiência de Conferência dos usuários durante a migração do Lync 2010. Para obter mais detalhes sobre como os clientes do Lync Server 2013 podem coexistir e interagir com versões anteriores do cliente e do servidor, consulte [interoperabilidade do cliente no Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Ingressar em reuniões do Lync Server 2010 com um cliente do Lync 2013

Durante a migração do Lync Server 2010, pode haver um período de coexistência quando os usuários ingressarem em reuniões do Lync Server 2010 com um cliente do Lync 2013. Esses usuários têm acesso aos recursos do cliente Lync 2013 com as seguintes exceções:

  - Nas opções de gerenciamento de **participantes** , que podem ser acessadas apontando para o ícone pessoas na janela da reunião, a opção **sem im de reunião** não funciona.

  - O modo de exibição de galeria não funciona em videoconferências. O usuário vê apenas o alto-falante ativo em vez de todos os alto-falantes. Na lista de opções de **escolha um layout, o modo de** exibição de **Galeria** não está disponível

  - A lista de participantes é exibida por padrão em videoconferências.

  - Ao clicar com o botão direito do mouse em um usuário na lista de participantes, as opções **bloquear o gerenciamento do participante de vídeo** e **fixar na Galeria** não estarão disponíveis.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Experiência do usuário durante a migração do Office Communications Server 2007 R2

Esta seção fornece um resumo da experiência de Conferência dos usuários durante a migração do Office Communications Server 2007 R2, antes e depois do Lync 2013 ser instalado. Para obter mais detalhes sobre como os clientes do Lync Server 2013 podem coexistir e interagir com versões anteriores do cliente e do servidor, consulte [interoperabilidade do cliente no Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Após a migração da conta de usuário, antes da instalação do Lync 2013

Após um usuário ser migrado para o servidor do Lync Server 2013, mas antes que novos clientes sejam instalados, os usuários do Office Communicator 2007 R2 podem continuar a usar o cliente existente no Lync Server 2013 para recursos de presença e IM, mas não há suporte para recursos de conferência.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Após a migração da conta de usuário, após a instalação do Lync 2013

Quando um usuário migrado instala o Lync 2013, o suplemento de reunião online para Lync 2013 também é instalado. Isso possui os seguintes efeitos:

  - Todas as reuniões programadas subsequentemente usam o novo formato de reunião, que utiliza um endereço https:// ao invés do endereço meet:// Live Meeting herdado.

  - Em uma implantação gerenciada por ti do Lync 2013, o administrador tem a opção de desinstalar o suplemento de conferência do Microsoft Office Outlook, que é usado para agendar o Live Meeting Server e reuniões baseadas em serviços. No entanto, você pode ter usuários que precisam continuar a programar reuniões de serviço do Live Meeting. Neste caso, é possível permitir que os suplementos coexistam.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Reuniões com organizações federadas que usam clientes anteriores

Os usuários em organizações federadas que usam o Microsoft Office Communicator 2007 não podem ingressar em reuniões do Lync Server 2013 em sua organização se essas reuniões estiverem bloqueadas pelo organizador. Você precisa reagendar essas reuniões no Lync Server 2013 para que os participantes federados ingressem na reunião usando a nova URL de reunião do https://, eles podem usar o Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

