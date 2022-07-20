---
title: Políticas de número de chamada gratuita de Audioconferência
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: Saiba mais sobre como a Audioconferência no Microsoft 365 ou Office 365 permite que os usuários liguem para reuniões de seus telefones.
ms.openlocfilehash: 1a03faf129a40d61605474e95c759067ce20841e
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884900"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>Configurações de política de audioconferência para números de chamada tarifada e gratuita

## <a name="teams-audio-conferencing-policy"></a>Política de Audioconferência do Teams

Use políticas de audioconferência para gerenciar números de chamada tarifada e gratuita de audioconferência a serem exibidos em convites de reunião criados por usuários em sua organização. Você pode usar uma das duas políticas criadas automaticamente ou criar e atribuir políticas personalizadas. As duas políticas criadas automaticamente são globais (padrão em toda a organização) e AllowTollFreeDialinFalse (atribuídas a todos os usuários existentes na organização que não estão habilitados para números de discagem gratuita). Você gerencia políticas de audioconferência no centro de administração do Microsoft Teams ou usando o [PowerShell](teams-powershell-overview.md).

- A configuração de AllowTollFreeDialin não pode mais ser gerenciada para um usuário individual por meio do Centro de administração do Teams ou do PowerShell. Os administradores de locatários só poderão gerenciar essa configuração por meio da nova política de audioconferência.
- A política global não pode ser modificada do centro de administração do Teams.

Quando uma política de audioconferência do Teams estiver habilitada no locatário, haverá duas políticas criadas automaticamente disponíveis no locatário. As duas políticas criadas automaticamente e suas configurações padrão são:

### <a name="global-org-wide-default"></a>Global (padrão em toda a organização)

Nesta política, o valor de **AllowTollfreedialin** será definido como ON e não haverá nenhum número de telefone definido na política. Essa será a Política padrão para todos os usuários no locatário que, no momento do lançamento, têm **AllowTollfreedialin** definido como **Ativado**.
Como a política não tem nenhum número de telefone definido, quando os usuários dessa política criam uma reunião do Teams, os números de telefone disponíveis em sua reunião serão os mesmos números de telefone que os usuários tinham antes da política. Esses números de telefone normalmente são padrão para o país/local do usuário, a menos que sejam alterados pelo administrador do locatário para usuários individuais.

Por exemplo, se um usuário da Alemanha tiver o número de telefone de chamada tarifada e gratuita da Alemanha atribuído antes do lançamento da política de Audioconferência, no início, o usuário receberá a política global e os números de telefone que ele continuará vendo no convite da reunião serão os mesmos de antes da aplicação da política (ou seja,  os números de chamada tarifada e gratuita alemãs). Um usuário final não verá nenhuma alteração quando a política for iniciada. No entanto, se um administrador de locatários modificar a Política Global e incluir números de telefone específicos na política que são diferentes de antes, todos os usuários da política verão apenas os números de telefone incluídos na política em todas as reuniões agendadas.

> [!NOTE]
> Se, em vez de modificar a política global, um administrador de locatários criar uma política personalizada e a aplicar aos usuários, as configurações definidas na política personalizada serão as que os usuários finais verão em seus convites de reunião.

Por exemplo, se a política personalizada tiver "AllowTollFreeDialinFalse" e não tiver nenhum número de telefone definido, os usuários dessa política não poderão ter números de chamada gratuita e, como nenhum número de telefone é definido na política, o número de telefone de chamada tarifada que será usado em convites de reunião criados por esses usuários serão os mesmos números de telefone que os usuários tinham antes da política. Esses números de telefone normalmente são padrão para o país/local do usuário, a menos que sejam alterados pelo administrador do locatário para usuários individuais.

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

Nesta política, o valor de **AllowTollfreedialin** será definido como **Desativado** e não haverá nenhum número de telefone definido na política. Essa será a política padrão para todos os usuários no locatário que, no momento do lançamento, têm **AllowTollfreedialin** definido como **Desativado**.

Como a política não tem nenhum número de telefone definido, quando os usuários dessa política criam uma reunião de equipe, os números de telefone que estarão disponíveis em sua reunião seriam os mesmos números de telefone que os usuários tinham antes da política. Esses números de telefone normalmente são padrão para o país, a região ou o local do usuário, a menos que isso tenha sido alterado pelo administrador do locatário para usuários individuais.

Por exemplo, se um usuário da Alemanha tiver um número de telefone de chamada tarifada da Alemanha atribuído antes do lançamento de uma política de Audioconferência, no início, o usuário receberá a política "AllowTollfreedialinFalse" e os números de telefone que ele continuará vendo no convite da reunião serão os mesmos de antes (ou seja, o número de chamada tarifada da Alemanha). Um usuário final não verá nenhuma alteração quando a política for iniciada. No entanto, se um administrador de locatários modificar a política **AllowTollfreedialinFalse** e incluir números de telefone específicos na política, todos os usuários da política verão apenas os números de telefone incluídos na política em todas as reuniões agendadas.

## <a name="create-a-custom-audio-conferencing-policy"></a>Criar uma política de audioconferência personalizada

Uma visão geral das etapas:

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para Reuniões > Audioconferência.
1. Selecione Adicionar.
1. Insira o nome e a descrição da política. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres.
1. Escolha as configurações que deseja.
1. Selecione Salvar.

Por exemplo, você pode ter um grupo de usuários que regularmente têm reuniões com participantes de mais de um país. Em nosso exemplo, os participantes são do Canadá, botswana e Singapura e todos eles querem ingressar na reunião por meio de audioconferência discando um número de telefone. Você pode criar uma nova política personalizada chamada "Canadá Botswana Singapore" e selecionar números de telefone desses três países para serem incluídos na política por meio  da opção Adicionar um número de telefone e salvar essa política. Em seguida, você pode atribuir essa política aos usuários necessários.

Isso garante que os números de telefone que você selecionou para Canadá, Botswana e Singapura serão incluídos nos convites de reuniões criados pelos usuários dessa política.

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>Instruções passo a passo sobre como criar uma política personalizada com base no exemplo

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, acesse **a** > **Audioconferência de Reuniões**.
2. Selecione **Adicionar**.
3. Insira o nome e a descrição da política. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres.
4. Escolha se deseja ou não incluir números de chamada gratuita em reuniões criadas por usuários dessa política. Definir isso como **Ativado** permitirá que você adicione números de telefone gratuitos nesta política.
5. Selecione Adicionar um número de telefone.
6. Um painel será aberto à direita da tela, contendo a **caixa Pesquisar por** local.
7. Entre no Canadá e selecione um número de telefone do Canadá nos resultados.
8. Selecione **Adicionar**.
9. Repita as etapas 6 e 7 da mesma maneira para pesquisar e adicionar números de telefone de Botswana e Singapura.
10. Selecione números de chamada gratuita se você tiver ativado a configuração Incluir números de chamada gratuita em reuniões criadas por usuários dessa **política na etapa** 4.
11. Selecione **Adicionar** no canto inferior direito do painel. Os números de telefone dos três países selecionados serão listados.
12. Há uma coluna de classificação que determina a ordem na qual os números de telefone serão exibidos em convites de reuniões criados por usuários dessa política. Você pode alterar a ordem selecionando um número de telefone e movendo-o para cima ou  para baixo usando  os botões Mover para cima e Mover para baixo, respectivamente.
13. Depois de colocar os números de telefone na ordem de sua preferência, selecione **Salvar**.
14. Sua política personalizada chamada "Canada Botswana Singapore" é criada.
15. Depois que a criação for concluída, você poderá atribuir essa política aos usuários.

## <a name="edit-a-meeting-policy"></a>Editar uma política de retenção

Você pode editar todas as políticas personalizadas que criar. (Observe que a política global não pode ser editada no centro de administração do Teams)

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, acesse **a** > **Audioconferência de Reuniões**.
1. Escolha a política que você deseja editar selecionando à esquerda do nome da política e, em seguida, **selecionando Editar**.
1. Faça edições.
1. Selecione **Salvar**.

> [!NOTE]
> Você não pode excluir uma política se usuários estiverem atribuídos a ela. Você precisará atribuir uma política diferente a todos os usuários afetados e, em seguida, poderá excluir a política original.

## <a name="assign-a-meeting-policy-to-users"></a>Atribuir uma política de reunião aos usuários

> [!IMPORTANT]
> Depois que uma nova política de Audioconferência for aplicada a um usuário, os números de telefone definidos na política só estarão disponíveis em novas reuniões criadas pelo usuário com essa política. Todas as reuniões antigas e recorrentes agendadas antes da política continuarão a mostrar as configurações antigas, por exemplo, uma chamada tarifada e um número de chamada gratuita (se a chamada gratuita tiver sido habilitada para esse usuário). Um cenário aqui pode ser que um usuário tenha  habilitado Permitir Chamada Gratuita e tenha um número de chamada gratuita atribuído e tenha criado reuniões recorrentes para o futuro. Nesse cenário, se você criar uma política personalizada com AllowTollfreeDialIn desativado e  aplicá-la a esse usuário, as novas reuniões criadas por esse usuário não incluirão números de chamada gratuita, mas as reuniões antigas e recorrentes ainda mostrarão números de chamada gratuita. Portanto, se os chamadores discam esse número de chamada gratuita para ingressar na reunião, a chamada falhará porque a chamada gratuita agora está desabilitada para esse usuário devido à política. Para evitar isso, você pode migrar as reuniões antigas dos usuários depois de atribuir a eles a nova política de audioconferência. Examine o [uso do SERVIÇO de Migração de Reunião (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

Você pode atribuir uma política diretamente aos usuários ou a um grupo do qual os usuários são membros (se houver suporte para o tipo de política), individualmente ou em números maiores por meio de uma atribuição em lote (se houver suporte para o tipo de política).

Para saber mais sobre as diferentes maneiras de atribuir políticas aos usuários, consulte [Atribuir políticas a usuários e grupos](assign-policies-users-and-groups.md).

> [!NOTE]
> Um usuário pode receber apenas uma política de audioconferência por vez.

> [!IMPORTANT]
> Pode levar até 24 horas para que os números de telefone atribuídos apareçam no convite da reunião. Se você não estiver vendo os números atualizados serem exibidos, aguarde pelo menos 24 horas antes de entrar em contato com o suporte.

### <a name="known-issue"></a>Problema conhecido

Quando você inicia uma reunião usando a  opção Reunir agora do Microsoft Teams > Calendário > Reunir Mow, se você selecionar as reticências... e, em seguida, informações de reunião, haverá um problema com a parte inferior da seção em **Ou chamar (somente áudio)**. Todos os números de telefone definidos na política serão mostrados, mas o alinhamento dos números dificulta a leitura.
