---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Skype for Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são fones de áudio e faxes analógicos. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos em seu ambiente do Skype for Business Server. Depois de migrar para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use o Shell de Gerenciamento do Skype for Business Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mova esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752823"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

O Skype for Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos suportados são fones de áudio e faxes analógicos. Você pode configurar os gateways qualificados para dar suporte ao uso de dispositivos analógicos em seu ambiente do Skype for Business Server. Depois de migrar para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados aos dispositivos analógicos. Use o Shell de Gerenciamento do Skype for Business Server para recuperar primeiro todos os objetos de contato associados aos dispositivos analógicos herdados e, em seguida, mova esses objetos para o pool do Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Na linha de comando, digite:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verifique se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019. Na linha de comando, digite:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.


