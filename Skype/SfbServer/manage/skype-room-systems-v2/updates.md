---
title: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gerenciar atualizações do Windows para salas do Microsoft Teams
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103197"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

As Salas do Microsoft Teams são executados no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebem as mesmas versões do Sistema Operacional e Atualizações do Windows como uma área de trabalho padrão.

As Atualizações do Windows podem ser gerenciadas de algumas maneiras diferentes:

## <a name="hands-off-approach"></a>Abordagem prática 
- As atualizações podem ser baixadas diretamente do Windows Updates automaticamente e instaladas durante o horário de folga. Se nenhuma alteração for feita na configuração, este será o estado padrão.
- Atualizações não adiáveis instalarão o primeiro dia da versão automaticamente. 
- Atualizações de qualidade e drivers baixarão e instalarão o primeiro dia automaticamente. 
- Atualizações de Recursos. Consulte observações adicionais abaixo. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Atualizações do Windows para Empresas](/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- As atualizações são baixadas do WU ou do WSUS, mas com atrasos configurados após a data de lançamento original do KB. 
- Combinado com várias políticas de OU ou filtradas, isso permite a criação de "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam atualizações de qualidade primeiro e quais serão instalados posteriormente. Isso permite testes de confiabilidade e desempenho em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar atualizações do Windows no Microsoft Endpoint Configuration Manager, por exemplo.
- O WSUS e o Windows [](/windows/deployment/update/waas-integrate-wufb) Updates para Empresas podem ser configurados ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle que o Windows Updates for Business fornece.
- Atualizações de recursos. Consulte observações adicionais abaixo.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update para Empresas, mas com a opção adicional de direcionar KBs específicos em cada "anel" ou toda a implantação. Cada Atualização pode ser implantada individualmente e testada à vontade, em vez de depender apenas de um atraso. 
- Atualizações de recursos. Consulte observações adicionais abaixo.


### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de Qualidade e Não Adiáveis, as "Atualizações de Recursos" do Windows 10 (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com salas do Microsoft Teams. Mesmo que ele seja lançado para o Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou até mesmo manualmente pressionado por suas próprias tentativas ou configurações, ele não permitirá a instalação até que o bloco em nossa extremidade seja removido.

A Sala do Microsoft Teams "in-box", usando a abordagem de hands-off, não instalará um Windows Update ou reiniciará um dispositivo automaticamente por causa de uma Atualização do Windows. No entanto, os sistemas podem baixar uma atualização e aguardar a próxima reinicialização para instalá-la. A menos que alguém o reinicie manualmente, a instalação deve ocorrer na reinicialização automática noturna. As Atualizações do Windows devem ser transparentes na sala, a interface do usuário nunca deve ser interrompida pelas Atualizações do Windows.

Se você optar por ingressar no domínio, use o Microsoft Endpoint Configuration Manager ou o WSUS e preste atenção especial a políticas ou ações que podem resultar na instalação de uma atualização ou forçando uma reinicialização durante o horário comercial. Se você tiver sistemas em sua implantação reiniciando durante o uso ou alertando sobre atualizações do Windows pela interface do usuário, você vai querer ver sua configuração.