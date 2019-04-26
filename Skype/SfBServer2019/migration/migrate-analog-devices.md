---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos com suporte são telefones áudio analógicos e máquinas de fax analógicos. Você pode configurar os gateways qualificados para o suporte ao uso de dispositivos analógicos na sua Skype para ambiente de servidor de negócios. Após migrar para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados com os dispositivos analógicos. Use Skype do Shell de gerenciamento do servidor de negócios para o primeiro recuperar todos os objetos associados com os dispositivos analógicos herdados do contato e mova esses objetos para o Skype para Business Server 2019 pool.
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238387"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype para Business Server oferece suporte para dispositivos analógicos. Especificamente, os dispositivos analógicos com suporte são telefones áudio analógicos e máquinas de fax analógicos. Você pode configurar os gateways qualificados para o suporte ao uso de dispositivos analógicos na sua Skype para ambiente de servidor de negócios. Após migrar para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados com os dispositivos analógicos. Use Skype do Shell de gerenciamento do servidor de negócios para o primeiro recuperar todos os objetos associados com os dispositivos analógicos herdados do contato e mova esses objetos para o Skype para Business Server 2019 pool.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.

2. Na linha de comando, digite:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verifique se todos os objetos de contato foram movidos para o Skype para Business Server 2019 pool. Na linha de comando, digite:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verifique se todos os objetos de contato estão agora associados com o Skype para Business Server 2019 pool.


