---
title: Gerenciar Windows atualizações para Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: O administrador pode aprender sobre como gerenciar Windows atualizações e Windows de recursos para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b99e8869ed9fa63a372c6c40d1d0d2be28c019
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503748"
---
# <a name="manage-windows-updates"></a>Gerenciar Windows atualizações

Salas do Microsoft Teams é executado em Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas Windows atualizações e builds do sistema operacional como um computador de área de trabalho padrão.

Windows atualizações podem ser gerenciadas conforme discutido nas seções a seguir:

## <a name="hands-off-approach"></a>Abordagem prática 

- Por padrão, as atualizações são baixadas diretamente Windows atualizações automaticamente e instaladas durante o horário de folga.
- Atualizações não adiáveis instalam automaticamente o primeiro dia da versão.
- Atualizações de qualidade e drivers baixam e instalam automaticamente o primeiro dia.
- Atualizações de recursos. Consulte as anotações a seguir.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Atualizações para Empresas (GPO ou Intune)  

- [Windows download de Atualizações para Empresas](/windows/deployment/update/waas-manage-updates-wufb)
- As atualizações são baixadas do Windows Update ou do seu Windows Server Update Services (WSUS), mas com atrasos configurados após a data de lançamento original.
- Você pode usar várias OUs ou políticas filtradas para criar "anéis" de implantação, onde os administradores podem especificar quais dispositivos Salas do Teams instalar atualizações de qualidade primeiro e quais serão instalados posteriormente. A confiabilidade e o desempenho podem ser testados em um subconjunto de dispositivos antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar Windows Atualizações no Configuration Manager.
- O WSUS e Windows Atualizações para Empresas podem ser configuradas [](/windows/deployment/update/waas-integrate-wufb) ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle Windows Atualizações para Empresas fornece.
- Atualizações de recursos. Consulte as anotações a seguir.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Download do WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido Windows Atualizar para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação. Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.
- Atualizações de recursos. Consulte as anotações a seguir.

### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de Qualidade e Não Adiáveis, Windows 10 "Atualizações de Recursos" (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com Salas do Microsoft Teams. Mesmo que a atualização seja lançada no Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou pressionado manualmente, o Salas do Microsoft Teams não permitirá que a atualização não testada seja instalada.

Salas do Microsoft Teams funções "out-of-box" com uma abordagem prática. Salas do Teams baixe uma atualização e aguarde a próxima reinicialização para instalá-la. A menos que alguém o reinicia manualmente, a instalação só acontece na reinicialização automática noturna. Windows as atualizações devem ser transparentes na sala, e a operação normal nunca deve ser interrompida por Windows Atualizações.

Se você optar por ingressar em dispositivos de junção de domínio, poderá usar Microsoft Endpoint Configuration Manager ou WSUS. Preste atenção especial a políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial. Salas do Teams não deve ser reiniciado durante o uso ou alerta sobre Windows atualizações na interface do usuário durante o horário de uso. Revise sua configuração se esse comportamento acontecer.
