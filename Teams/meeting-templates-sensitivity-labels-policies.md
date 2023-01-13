---
title: Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como usar políticas de administrador do Teams junto com rótulos de confidencialidade e modelos de reunião para aprimorar a segurança e a conformidade para reuniões confidenciais.
ms.openlocfilehash: f0363a7e27df39da7270d9f492048b639f8a3d30
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800077"
---
# <a name="use-teams-meeting-templates-sensitivity-labels-and-admin-policies-together-for-sensitive-meetings"></a>Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Nas reuniões do Teams, os organizadores da reunião podem configurar [uma variedade de configurações](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) que determinam quais recursos estão disponíveis na reunião. Como administrador, você pode desabilitar ou impor valores específicos para essas configurações usando uma combinação de políticas de administrador, rótulos de confidencialidade e modelos de reunião.

[Os modelos de reunião](custom-meeting-templates-overview.md) são criados e gerenciados no centro de administração do Teams. Rótulos de confidencialidade são criados e manged no portal de conformidade do Microsoft Purview. 

> [!Note]
> As configurações de reunião em rótulos de confidencialidade e modelos de reunião personalizados exigem Teams Premium.

Usando políticas de administrador, modelos e rótulos juntos, você pode tornar possível uma variedade de cenários de reunião para ajudar a atender às necessidades de conformidade e negócios para os diferentes departamentos da sua organização.

## <a name="policies-labels-templates-and-meetings-settings"></a>Políticas, rótulos, modelos e configurações de reuniões

A tabela a seguir mostra uma lista de recursos do Teams que podem ser úteis para gerenciar reuniões com diferentes necessidades de conformidade em sua organização e onde elas podem ser configuradas.

|Recurso|Política de administrador do Teams|Rótulo de confidencialidade|Modelo de reunião|Organizador da reunião|
|:----|:----|:----|:----|:----|
|Permitir câmera para participantes|As configurações de política de administração de vídeo IP e Modo para IP determinam quais participantes podem usar suas câmeras.|Nenhuma configuração|Pode impedir ou permitir a câmera para os participantes. A configuração pode ser imposta ou o organizador da reunião pode ser autorizado a alterar.|Pode impedir ou permitir a câmera para os participantes se não estiver bloqueado por um modelo.|
|Permitir microfone para participantes|A configuração de áudio Modo para IP determina quais participantes podem usar seus microfones.|Nenhuma configuração|Pode impedir ou permitir microfone para os participantes. A configuração pode ser imposta ou o organizador da reunião pode ser autorizado a alterar.|Pode impedir ou permitir o microfone para os participantes se não estiver bloqueado por um modelo.|
|Aplicar uma marca d'água ao feed de vídeo de todos|Pode ser definido como Ativado ou Desativado. Se definido como Desativado, não estará disponível em rótulos de confidencialidade, modelos de reunião ou configurações de reunião.|Pode impor ou impedir marcas d'água nos feeds de vídeo dos participantes ou deixar a configuração descontrolada.|Pode impor ou impedir marcas d'água nos feeds de vídeo dos participantes, a menos que a configuração seja controlada por um rótulo de confidencialidade.|O organizador da reunião pode ativar ou desativar, a menos que a configuração seja desabilitada pela política de administrador ou imposta ativada ou desativada por um modelo de reunião ou rótulo de confidencialidade.|
|Aplicar uma marca d'água ao conteúdo compartilhado|Pode ser definido como Ativado ou Desativado. Se definido como Desativado, não estará disponível em rótulos de confidencialidade, modelos de reunião ou configurações de reunião.|Pode impor ou impedir marcas d'água no conteúdo compartilhado na tela ou deixar a configuração descontrolada.|Pode impor ou impedir marcas d'água no conteúdo compartilhado na tela, a menos que a configuração seja controlada por um rótulo de confidencialidade.|O organizador da reunião pode ativar ou desativar, a menos que a configuração seja desabilitada pela política de administrador ou imposta ativada ou desativada por um modelo de reunião ou rótulo de confidencialidade.|
|Criptografia de ponta a ponta|Quando Ativado, a criptografia de ponta a ponta pode ser ativada por um rótulo de confidencialidade, um modelo de reunião ou o organizador da reunião.|Pode impor ou impedir a criptografia de ponta a ponta ou deixar a configuração descontrolada.|Pode impor ou impedir a criptografia de ponta a ponta, a menos que a configuração seja controlada por um rótulo de confidencialidade.|O organizador da reunião pode ativar ou desativar, a menos que a configuração seja desabilitada pela política de administrador ou imposta ativada ou desativada por um modelo de reunião ou rótulo de confidencialidade.|
|Gerenciar o que os participantes veem|Nenhuma configuração|Nenhuma configuração|Pode ser definido como Ativado ou Desativado e pode impor a configuração ou permitir que o organizador da reunião altere-a.|O organizador da reunião pode ativar ou desativar, a menos que a configuração seja imposta ou desativada por um modelo de reunião.|
|Chat de reunião|Pode ser definido como Ativado, Desativado ou Ativado para todos, exceto participantes anônimos. Se definida como Desativada, a configuração de chat será desabilitada em rótulos, modelos e configurações de reunião.|Pode impor o chat para ativar, desativar ou somente reunião ou deixar a configuração descontrolada.|Se habilitado na política de administrador e não controlado por um rótulo de confidencialidade, poderá ser definido como Ativado, Desativado ou somente reunião. A configuração pode ser imposta ou o organizador da reunião pode ser autorizado a alterar.|Se habilitado pela política de administrador e não for imposto por um rótulo ou modelo de confidencialidade, o proprietário da reunião poderá definir como Ativado, Desativado ou somente reunião.|
|Pessoas discagem pode ignorar o lobby|Define a configuração padrão para novas reuniões.|Se o rótulo estiver controlando quem pode ignorar o lobby, essa configuração será imposta ativa ou desativada, caso contrário, ela será descontrolada.|Se não for controlado por um rótulo de confidencialidade, poderá ser definido como Ativado ou Desativado. A configuração pode ser imposta ou o organizador da reunião pode ser autorizado a alterar.|Se não for imposta por um rótulo ou modelo de confidencialidade, o proprietário da reunião poderá definir como Ativado ou Desativado.|
|Impedir a cópia do conteúdo do chat na área de transferência|Nenhuma configuração|Pode impedir que o chat da reunião seja copiado. (Não se aplica a participantes anônimos.)|Nenhuma configuração|Nenhuma configuração|
|Gravar automaticamente|Nenhuma configuração|Pode impor ou impedir a gravação automática da reunião ou ficar descontrolado.|Se não for controlado por um rótulo de confidencialidade, pode ser definido como Ativado ou Desativado e pode impor a configuração ou permitir que o organizador da reunião altere-a.|O organizador da reunião pode ativar ou desativar, a menos que a configuração seja imposta ou desativada por um modelo de reunião ou rótulo de confidencialidade.|
|Quem pode ignorar o lobby|Define a configuração padrão para novas reuniões.|Pode impor uma opção específica para quem pode ignorar o lobby ou pode ficar descontrolado.|Se não for controlado por um rótulo de confidencialidade, selecione uma configuração para quem pode ignorar o lobby. A configuração pode ser imposta ou o organizador da reunião pode ser autorizado a alterar.|O organizador da reunião pode escolher quem pode ignorar o lobby, a menos que a configuração seja imposta por um rótulo ou modelo.|
|Quem pode apresentar|Define a configuração padrão para novas reuniões. Os valores disponíveis são Organizadores, Todos na organização e Todos.|Pode impor configurações de todos, participantes autenticados, organizadores ou pessoas específicas ou pode ficar descontrolado.|Nenhuma configuração|O organizador da reunião pode selecionar quem pode apresentar, a menos que seja imposto por um rótulo de confidencialidade.|
|Quem pode gravar|Nenhuma configuração|Pode impor configurações de organizadores ou organizadores e apresentadores ou pode ficar descontrolado.|Se não for controlado por um rótulo de confidencialidade, selecione uma configuração de organizadores ou organizadores e apresentadores.  A configuração pode ser imposta ou o organizador da reunião pode ser autorizado a alterar.|O organizador da reunião pode escolher quem pode gravar - organizadores ou organizadores e apresentadores - a menos que a configuração seja imposta por um rótulo ou modelo.|

## <a name="admin-policies-effect-on-sensitivity-labels-and-meeting-templates"></a>Administração efeito das políticas sobre rótulos de confidencialidade e modelos de reunião

Embora algumas políticas de administrador - como configurações de lobby e que podem apresentar - especifiquem padrões que o organizador da reunião pode alterar, a maioria das políticas de administrador determina se um determinado recurso está disponível para os usuários.

Se um recurso não estiver disponível para um determinado usuário porque a política de administrador a desativou para eles, esse recurso não poderá ser imposto por um rótulo de confidencialidade ou modelo de reunião.

Por exemplo, se você criar um rótulo *altamente confidencial* e configurá-lo para impor a marca d'água e a criptografia de ponta a ponta, essa aplicação só ocorrerá se a marca d'água e a criptografia de ponta a ponta estiverem habilitadas para o organizador da reunião na política de administração.

Conforme você planeja seus modelos de reunião e rótulos de confidencialidade, verifique se as configurações que você deseja controlar com eles estão habilitadas em políticas de administrador quando necessário.

## <a name="sensitivity-labels-and-templates-together"></a>Rótulos e modelos de confidencialidade juntos

Algumas configurações só estão disponíveis em rótulos de confidencialidade e algumas estão disponíveis apenas em modelos. Vários estão disponíveis em ambos:

- Chat
- Criptografia de ponta a ponta
- Configurações de lobby
- Gravação de reunião
- Watermarking

Sempre que um rótulo de confidencialidade é usado, as configurações configuradas no rótulo têm precedência sobre qualquer modelo ou configurações de organizador de reunião.

As configurações em um rótulo de confidencialidade podem ser deixadas descontroladas quando o rótulo é criado, permitindo que um modelo ou o organizador da reunião controle essas configurações.

Os rótulos de confidencialidade geralmente são usados para várias finalidades - rotulando documentos, sites e emails, bem como reuniões. Você pode evitar a criação de rótulos adicionais que são apenas para reuniões usando modelos junto com os rótulos para considerar as variações em um determinado tipo de reunião.

Por exemplo, seu departamento de marketing pode ter requisitos diferentes para reuniões confidenciais do que o departamento de pesquisa. Você pode configurar as configurações comuns a ambos em um rótulo de confidencialidade e, em seguida, disponibilizar modelos separados para os dois grupos que refinam ainda mais as configurações de reunião para esse grupo. Ambos os modelos poderiam usar o mesmo rótulo.

## <a name="user-based-policies-and-meeting-based-policies"></a>Políticas baseadas no usuário e políticas baseadas em reunião

As políticas do Teams - incluindo políticas de reunião - se aplicam no nível do usuário ou do grupo. As configurações de rótulo e modelo de confidencialidade se aplicam no nível de reunião individual em que esses rótulos e modelos são usados. Considere onde faz sentido configurar configurações em políticas de administrador do Teams versus rótulos ou modelos de confidencialidade.

Seguem alguns exemplos:

Se você quiser diferentes configurações de lobby padrão para o departamento de pesquisa e o departamento de marketing, poderá configurar esses padrões usando políticas de administrador e modificá-las ainda mais com rótulos ou modelos.

Se você quiser marcas d'água disponíveis apenas para funcionários de governança, você pode habilitá-las apenas para essas pessoas que usam uma política de administrador. Em seguida, você pode ter rótulos ou modelos que imponham a marca d'água, mas a marca d'água só será usada em reuniões organizadas por funcionários de governança.

## <a name="different-meeting-types-with-the-same-sensitivity"></a>Tipos de reunião diferentes com a mesma confidencialidade

Usar modelos e rótulos juntos pode ser útil se você tiver diferentes tipos de reuniões que tenham a mesma confidencialidade. Por exemplo, se algumas de suas reuniões confidenciais forem interativas e algumas forem apresentações em que há interação mínima dos participantes, você poderá criar dois modelos:
- Um que desativa vídeo e áudio do participante a ser usado para apresentações
- Um que deixa vídeo e áudio a critério do organizador da reunião a ser usado para reuniões interativas

Ambos os modelos poderiam usar o rótulo *Sensitive* que controlaria configurações adicionais, como quem pode ignorar o lobby e quem pode apresentar.

## <a name="specify-default-values-that-meeting-organizers-can-change"></a>Especificar valores padrão que os organizadores da reunião podem alterar

Embora os rótulos geralmente imponham uma configuração específica, os modelos podem impor uma configuração ou permitir que o organizador da reunião a altere. Isso permite implementar configurações padrão que atendam às suas necessidades de conformidade, dando aos organizadores da reunião a opção de substituir a configuração, se apropriado.

Por exemplo, para um nível de proteção de linha de base, talvez você queira usar um rótulo de confidencialidade para desativar a marca d'água. Ao mesmo tempo, você pode usar um modelo para definir o padrão para quem pode ignorar o lobby, mas permitir que o organizador da reunião altere a configuração se precisar.

Você pode atribuir seu rótulo de proteção de linha de base ao modelo para que ambos sejam usados quando um organizador de reunião escolher esse modelo.

Algumas políticas de administrador também podem ser usadas para definir um valor padrão que pode ser alterado por um organizador de reunião. Estes incluem controles de lobby e quem pode apresentar.

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md)

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Usar rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings)
