---
title: Gerenciar o Windows Atualizações para Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: Administração saber mais sobre como gerenciar as atualizações de recursos do Windows Atualizações Windows para Salas do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272176"
---
# <a name="manage-windows-updates"></a>Gerenciar o Windows Atualizações

Salas do Microsoft Teams é executado em Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe os mesmos builds do sistema operacional e Atualizações windows como um computador desktop padrão.

Os Atualizações windows podem ser gerenciados conforme discutido nas seções a seguir:

## <a name="hands-off-approach"></a>Abordagem prática 

- Por padrão, as atualizações são baixadas diretamente do Windows Atualizações automaticamente e instaladas fora do horário comercial.
- Não adiável Atualizações instalar automaticamente o primeiro dia do lançamento.
- Os Atualizações e drivers baixam e instalam automaticamente o primeiro dia.
- Recursos Atualizações. Veja as anotações a seguir.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Atualizações for Business (GPO ou Intune)  

- [Download Atualizações Windows para Empresas](/windows/deployment/update/waas-manage-updates-wufb)
- Atualizações são baixados do Windows Update ou do Windows Server Update Services (WSUS), mas com atrasos configurados após a data de lançamento original.
- Você pode usar várias UOs ou políticas filtradas para criar "anéis" de implantação, em que os administradores podem especificar quais dispositivos Salas do Teams instalam o Quality Atualizações primeiro e quais são instalados posteriormente. A confiabilidade e o desempenho podem ser testados em um subconjunto de dispositivos antes de distribuir atualizações em toda a implantação sem a sobrecarga de gerenciar o Windows Atualizações em Configuration Manager.
- O WSUS e o Windows Atualizações para Empresas podem ser configurados ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle que o Windows Atualizações for Business fornece.[](/windows/deployment/update/waas-integrate-wufb)
- Atualizações de recursos. Veja as anotações a seguir.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Download do WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido Windows Update para Empresas, mas com a opção adicional de direcionar KBs específicos dentro de cada "anel" ou toda a implantação. Cada atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso.
- Atualizações de recursos. Veja as anotações a seguir.

### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de qualidade e não adiáveis, o Windows 10 "Feature Atualizações" (versões principais do sistema operacional) só será instalado após os testes da Microsoft e validará uma determinada funcionalidade de atualizações com o Salas do Microsoft Teams. Mesmo que a atualização seja liberada para o Canal do Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou enviado manualmente por push, o Salas do Microsoft Teams não permitirá a instalação da atualização não testada.

Salas do Microsoft Teams funções "fora de caixa" com uma abordagem prática. Salas do Teams baixar uma atualização e aguardar a próxima reinicialização para instalá-la. A menos que alguém o reinicialize manualmente, a instalação ocorrerá apenas na reinicialização automática noturna. As Atualizações windows devem ser transparentes na sala e a operação normal nunca deve ser interrompida pelo Windows Atualizações.

Se você optar por ingressar em dispositivos no domínio, poderá usar o Microsoft Endpoint Configuration Manager ou o WSUS. Preste atenção especial às políticas ou ações que resultam em uma atualização de dispositivo ou reinicialização forçada durante o horário comercial. Salas do Teams não deve reinicializar durante o uso ou alertar sobre o Windows Atualizações na interface do usuário durante o horário de uso. Examine sua configuração se esse comportamento ocorrer.
