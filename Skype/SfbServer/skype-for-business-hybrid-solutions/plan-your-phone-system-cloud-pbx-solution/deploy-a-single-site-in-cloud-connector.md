---
title: Implantar um único site no Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Saiba mais sobre a implantação de um único site PSTN no Cloud Connector Edition.
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358927"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Implantar um único site no Cloud Connector
 
> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Saiba mais sobre a implantação de um único site PSTN no Cloud Connector Edition.
  
Você pode implantar o Skype for Business Cloud Connector Edition com ou sem suporte para alta disponibilidade (HA). Se quiser habilitar a HA, você precisará implantar dois ou mais dispositivos dentro de um site. Você também pode converter um dispositivo existente para dar suporte à alta disponibilidade após sua implantação.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implantar o primeiro dispositivo do Skype for Business Cloud Connector Edition

Para implantar o primeiro dispositivo em um site, abra um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo:
  
```powershell
Register-CcAppliance
```

Siga as instruções para fornecer o nome e a senha da conta de administrador de locatários. Use a conta que você criou para o gerenciamento online do Cloud Connector. Além disso, siga as instruções para fornecer a senha do certificado externo, a senha do administrador do modo de segurança, a senha do administrador do domínio e a senha do administrador da VM. 
  
Na versão 1.4.2 e anteriores, também siga as instruções para fornecer a senha do certificado externo, a senha do administrador do modo de segurança, a senha do administrador do domínio e a senha do administrador da VM. 
  
Na versão 2,0 e posterior, também siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.
  
Para iniciar a instalação, abra um console do PowerShell como administrador e execute o seguinte cmdlet:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Adicionar um dispositivo a um site existente

Você pode estender um site existente do Cloud Connector para dar suporte à alta disponibilidade adicionando dispositivos adicionais ao site. 
  
1. Siga as etapas para preparar o dispositivo do Cloud Connector, conforme descrito em [preparar seu dispositivo do Cloud Connector](prepare-your-cloud-connector-appliance.md). Observe que algumas etapas são necessárias apenas para o primeiro dispositivo em sua implantação. Confirme se o diretório de sites existe e se está configurado corretamente para suporte de alta disponibilidade.
    
2. Execute o cmdlet a seguir apenas no servidor host recém-adicionado para atualizar as informações de topologia na sua configuração de organização do Microsoft 365 ou do Office 365. Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um:
    
   ```powershell
   Register-CcAppliance
   ```

3. Atualize a topologia em dispositivos existentes executando o seguinte cmdlet em cada servidor host. Só execute o cmdlet nos dispositivos existentes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Execute o cmdlet a seguir apenas em servidores de host recém-adicionados. Não execute esse cmdlet no dispositivo existente. Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se o diretório de sites foi definido como um caminho de pasta local, você precisará definir um compartilhamento de arquivos para esta pasta e usar um caminho UNC para o diretório de sites no novo dispositivo. Você pode deixar o primeiro diretório de site do dispositivo com o caminho local ou modificá-lo para usar o caminho UNC para o compartilhamento na mesma pasta. Se o local do diretório de sites compartilhado for alterado, qualquer equipamento instalado anteriormente precisará ser desinstalado e, em seguida, reinstalado. > importante: a senha da conta CceService e da conta CABackupFile deve ser a mesma em todos os dispositivos implantados no site, para que os dispositivos possam acessar o compartilhamento de diretório de sites e o arquivo de backup da AC criptografada no diretório de sites. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Remover um dispositivo de um site existente

Se você deseja remover um dispositivo de um site existente:
  
1. Execute o cmdlet a seguir apenas nos servidores host que você deseja remover do site para atualizar as informações de topologia em sua configuração de organização do Microsoft 365 ou do Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Execute o cmdlet a seguir apenas nos servidores host dos quais você deseja remover todas as máquinas virtuais do dispositivo.
    
   ```powershell
   Uninstall-CcAppliance
   ```


