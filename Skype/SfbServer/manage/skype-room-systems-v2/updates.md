---
title: Gerenciar atualizações do Windows para Salas do Microsoft Teams
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
description: Gerenciar atualizações do Windows para Salas do Microsoft Teams
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832871"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

As Salas do Microsoft Teams são executados no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebem as mesmas atualizações do Windows Update e builds do sistema operacional como uma área de trabalho padrão.

As atualizações do Windows podem ser gerenciadas de algumas maneiras diferentes:

## <a name="hands-off-approach"></a>Abordagem prática 
- As atualizações podem ser baixadas diretamente do Windows Update automaticamente e instaladas fora do horário comercial. Se nenhuma alteração for feita na configuração, esse será o estado padrão.
- As Atualizações Não Adiáveis instalarão automaticamente o primeiro dia do lançamento. 
- As Atualizações de Qualidade e os drivers baixarão e instalarão o dia um automaticamente. 
- Atualizações de Recursos. Veja observações adicionais abaixo. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Atualizações do Windows para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- As atualizações são baixadas do WU ou do WSUS, mas com atrasos configurados além da data de lançamento original da KB. 
- Combinado com várias UOs ou políticas filtradas, isso permite a criação de "anéis" de implantação, onde os administradores podem especificar quais dispositivos instalam primeiro as Atualizações de Qualidade e quais serão instaladas mais tarde. Isso permite testes de confiabilidade e desempenho em um subconjunto de sistemas antes de lançar atualizações em toda a implantação sem a sobrecarga de gerenciar atualizações do Windows no Microsoft Endpoint Configuration Manager, por exemplo.
- As atualizações do WSUS [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) e do Windows Update para Empresas podem ser configuradas ao mesmo tempo se você desejar o gerenciamento de largura de banda e o controle que o Windows Update para Empresas fornece.
- Atualizações de recursos. Veja observações adicionais abaixo.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update para Empresas, mas com a opção adicional de direcionar KBs específicos dentro de cada "anel" ou toda a implantação. Cada Atualização pode ser implantada e testada individualmente à vontade, em vez de depender apenas de um atraso. 
- Atualizações de recursos. Veja observações adicionais abaixo.


### <a name="feature-updates"></a>Atualizações de recursos

Ao contrário das atualizações de qualidade e não adiáveis, as "Atualizações de Recursos" do Windows 10 (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida uma determinada funcionalidade de atualizações com salas do Microsoft Teams. Mesmo que ele seja lançado para o Canal Semi-Annual (ou Direcionado se você tiver sistemas definidos para esse canal para teste) ou até mesmo manualmente pressionado por suas próprias tentativas ou configurações, ele não permitirá a instalação até que o bloco em nossa extremidade seja removido.

A Sala do Microsoft Teams "pronto para uso", usando a abordagem prática, não instalará um Windows Update ou reiniciará um dispositivo automaticamente por causa de um Windows Update. No entanto, os sistemas podem baixar uma atualização e aguardar a próxima reinicialização para instalá-la. A menos que alguém o reinicie manualmente, a instalação deve ocorrer na reinicialização automática noturna. As atualizações do Windows devem ser transparentes na sala, a interface do usuário nunca deve ser interrompida pelas atualizações do Windows.

Se você optar por ingressar no domínio, use o Microsoft Endpoint Configuration Manager ou o WSUS e preste atenção especial a políticas ou ações que podem resultar na instalação de uma atualização ou forçando uma reinicialização durante o horário comercial. Se você tiver sistemas na sua implantação reiniciando durante o uso ou alertas sobre as atualizações do Windows na interface do usuário, procure sua configuração.
