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
description: O administrador pode saber mais sobre como gerenciar atualizações do Windows e atualizações de recursos do Windows para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e52c1fdf3bb35be6869320aa57e6f5aff5fd0773
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905303"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

As Salas do Microsoft Teams são executados no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebem os mesmos builds do Sistema Operacional e Atualizações do Windows como um computador desktop padrão.

As atualizações do Windows podem ser gerenciadas conforme discutido nas seções a seguir:

## <a name="hands-off-approach"></a>Abordagem prática 

- Por padrão, as atualizações são baixadas diretamente das Atualizações do Windows automaticamente e instaladas durante o horário de folga.
- Atualizações não adiáveis instalam o primeiro dia do lançamento automaticamente.
- Atualizações de qualidade e drivers baixam e instalam o dia um automaticamente.
- Atualizações de recursos. Veja as anotações a seguir.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Atualizações do Windows for Business (GPO ou Intune)  

- [Download do Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- As atualizações são baixadas do Windows Update ou do WSUS, mas com atrasos configurados após a data de lançamento original.
- Você pode usar várias OUs ou políticas filtradas para criar "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalarão atualizações de qualidade primeiro e quais serão instalados mais tarde. A confiabilidade e o desempenho podem ser testados em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar as Atualizações do Windows no Configuration Manager.
- As atualizações do WSUS [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) e do Windows para Empresas podem ser configuradas ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle que o Windows Updates for Business fornece.
- Atualizações de recursos. Veja as anotações a seguir.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Download do WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update for Business, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou em toda a implantação. Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.
- Atualizações de recursos. Veja as anotações a seguir.

### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de Qualidade e Não Adiáveis, as "Atualizações de recursos" (versões principais do sistema operacional) do Windows 10 só serão instaladas após testes da Microsoft e validar uma determinada funcionalidade de atualizações com salas do Microsoft Teams. Mesmo que a atualização seja lançada para o Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou manualmente pressionado, um dispositivo do Microsoft Room Systems não permitirá que a atualização não testada seja instalada.

As Salas do Microsoft Teams funcionam "de forma automática" com uma abordagem prática e não instalarão um Windows Update ou reiniciarão um dispositivo automaticamente para um Windows Update. Os sistemas baixam uma atualização e aguardam a próxima reinicialização para instalá-la. A menos que alguém o reinicie manualmente, a instalação só acontecerá na reinicialização automática noturna. As atualizações do Windows devem ser transparentes na sala, e a operação normal nunca deve ser interrompida pelo Windows Update.

Se você optar por ingressar em dispositivos de domínio, use o Microsoft Endpoint Configuration Manager ou o WSUS. Preste atenção especial às políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial. Os sistemas em sua implantação não devem reiniciar durante o uso ou alerta sobre as Atualizações do Windows na interface do usuário durante as horas de uso, revise sua configuração se esse comportamento acontecer.