---
title: Gerenciar atualizações do Windows para salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gerenciar atualizações do Windows para salas de equipes da Microsoft
ms.openlocfilehash: 723ecf20fb835a3d942270e9de6d59416a9cd14a
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362550"
---
# <a name="manage-windows-updates"></a>Gerenciar atualizações do Windows

Salas de equipes da Microsoft é executado no Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas compilações de atualizações do Windows e o sistema operacional como uma área de trabalho padrão.

Atualizações do Windows podem ser gerenciadas de algumas maneiras diferentes:

## <a name="hands-off-approach"></a>Abordagem remota 
- Atualizações podem ser baixadas diretamente a partir de atualizações do Windows automaticamente e instaladas durante as horas inativas. Se nenhuma alteração é feita a configuração é o estado padrão.
- Atualizações de não-preteríveis instalará automaticamente um dia do lançamento. 
- Atualizações de qualidade e drivers irá baixar e instalar um dia automaticamente. 
- Atualizações de recurso. Consulte as Notas adicionais abaixo. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Atualizações do Windows para negócios](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO ou Intune)   
- As atualizações são baixadas do WU ou o WSUS, mas com atrasos configurados após a data de lançamento original do KB. 
- Combinados com várias OUs ou filtrada políticas, isso permite a criação de implantação "toques", onde os administradores podem especificar quais dispositivos instalar atualizações de qualidade primeiro e qual aquelas instalará posteriormente. Isso permite de confiabilidade e desempenho de teste em um subconjunto dos sistemas antes da aplicação do atualizações em toda a implantação sem a sobrecarga de gerenciamento de atualizações do Windows no SCCM por exemplo.
- WSUS e atualizações do Windows para a empresa podem ser [configurado ao mesmo tempo](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) se desejar que o gerenciamento de largura de banda e o controle de atualizações do Windows para a empresa fornece.
- Atualizações de recurso. Consulte as Notas adicionais abaixo.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Muito parecido com o Windows Update para negócios, mas com a opção adicional de direcionamento específico KB dentro de cada "anel" ou toda a implantação. Cada atualização pode ser individualmente implantados e testado à vontade, ao invés de confiar em apenas um atraso. 
- Atualizações de recurso. Consulte as Notas adicionais abaixo.


### <a name="feature-updates"></a>Atualizações de recurso

Ao contrário de atualizações de qualidade e não-Deferable, Windows 10 "Recurso atualizações" (versões principais do sistema operacional) só serão instaladas depois que a Microsoft testa e valida a funcionalidade de um determinado atualizações com salas de equipes da Microsoft. Mesmo se for liberado para o canal de delimitadas anual (ou multidifusão se você tiver sistemas definido como aquele canal para teste) ou até mesmo manualmente enviado por suas próprias configurações ou tentativas, ele não permitirá que a instalação até que o bloco de nosso end seja removido.

Microsoft equipes sala "out-of-box", usando as mãos desativa abordagem, não será instalar uma atualização do Windows ou reinicializar um dispositivo automaticamente por causa de uma atualização do Windows. No entanto, sistemas podem baixar uma atualização e aguarde a próxima reinicialização instalá-lo. A menos que alguém reinicializações-lo manualmente, instalação deve acontecer a reinicialização noturna automática. Atualizações do Windows deve ser transparentes na sala, a interface do usuário nunca deve ser interrompido por atualizações do Windows.

Se você optar por associação de domínio, use o SCCM ou WSUS e preste atenção especial nas diretivas ou ações que podem resultar em dispositivo instalar uma atualização ou forçar uma reinicialização durante o horário comercial. Se você tiver sistemas em sua implantação reinicializando durante o uso ou alertas sobre atualizações do Windows através da interface do usuário, você desejará examinar sua configuração.