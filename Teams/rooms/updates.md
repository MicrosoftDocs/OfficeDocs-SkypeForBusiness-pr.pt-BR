---
title: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: O administrador pode aprender sobre como gerenciar atualizações do Windows e atualizações de recursos do Windows para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117359"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

As Salas do Microsoft Teams são executados no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebem as mesmas versões do sistema operacional e atualizações do Windows como um computador de área de trabalho padrão.

As Atualizações do Windows podem ser gerenciadas conforme discutido nas seguintes seções:

## <a name="hands-off-approach"></a>Abordagem prática 

- Por padrão, as atualizações são baixadas diretamente do Windows Updates automaticamente e instaladas durante o horário de folga.
- Atualizações não adiáveis instalam o primeiro dia da versão automaticamente.
- Atualizações de qualidade e drivers baixam e instalam o primeiro dia automaticamente.
- Atualizações de recursos. Consulte as anotações a seguir.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Atualizações do Windows para Empresas (GPO ou Intune)  

- [Download do Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb)
- As atualizações são baixadas do Windows Update ou do WSUS, mas com atrasos configurados após a data de lançamento original.
- Você pode usar várias OUs ou políticas filtradas para criar "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados posteriormente. A confiabilidade e o desempenho podem ser testados em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar as Atualizações do Windows no Configuration Manager.
- O WSUS e o Windows Updates para Empresas podem ser configurados ao [mesmo](/windows/deployment/update/waas-integrate-wufb) tempo se você desejar o gerenciamento de largura de banda e o controle que o Windows Updates for Business fornece.
- Atualizações de recursos. Consulte as anotações a seguir.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Download do WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação. Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.
- Atualizações de recursos. Consulte as anotações a seguir.

### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de Qualidade e Não Adiáveis, o Windows 10 "Atualizações de Recursos" (versões principais do sistema operacional) só será instalado depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com salas do Microsoft Teams. Mesmo que a atualização seja lançada no Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou manualmente pressionado, um dispositivo microsoft room Systems não permitirá que a atualização não testada seja instalada.

As Salas do Microsoft Teams funcionam "in-locar" com uma abordagem prática e não instalarão um Windows Update ou reiniciarão um dispositivo automaticamente para um Windows Update. Os sistemas baixam uma atualização e aguardam a próxima reinicialização para instalá-la. A menos que alguém o reinicia manualmente, a instalação só acontece na reinicialização automática noturna. As Atualizações do Windows devem ser transparentes na sala e a operação normal nunca deve ser interrompida pelas Atualizações do Windows.

Se você optar por ingressar em dispositivos de junção de domínio, use o Microsoft Endpoint Configuration Manager ou o WSUS. Preste atenção especial a políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial. Os sistemas em sua implantação não devem ser reiniciados durante o uso ou alerta sobre as Atualizações do Windows pela interface do usuário durante o horário de uso, revise sua configuração se esse comportamento acontecer.