---
title: Provisionamento remoto e entrada para dispositivos Android do Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como provisionar e entrar remotamente em dispositivos Teams Android
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059185"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Provisionamento remoto e entrada para dispositivos Android do Teams

Os administradores de IT podem provisionar e entrar remotamente em um dispositivo Teams Android. Para provisionar um dispositivo remotamente, o administrador precisa carregar as IDs MAC dos dispositivos que estão sendo provisionados e criar um código de verificação. Todo o processo pode ser concluído remotamente a partir do Centro de administração do Teams.

## <a name="review-the-supported-devices"></a>Revisar os dispositivos com suporte

A lista a seguir mostra os requisitos de firmware de dispositivo Android.

|Categoria de dispositivo|Modelo de dispositivo|Versão do firmware|
|-|-|-|
|Telefones do Teams|Yealink T55/T56/T58|58.15.0.124|
|Telefones do Teams|Yealink VP59|91.15.0.58|
|Telefones do Teams|Yealink CP960|73.15.0.117|
|Telefones do Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|Telefones do Teams|Crestron UC-2|1.0.3.52|
|Telefones do Teams|  Poly Trio C60|  7.0.2.1071|
|Telefones do Teams|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Telefones do Teams|  Códigos de áudio C448HD/C450HD/C470HD|   1.10.120|

## <a name="add-a-device-mac-address"></a>Adicionar um endereço MAC de dispositivo

Conclua as etapas a seguir para provisionar um novo dispositivo.

1. Entre no Centro de administração do Teams.
2. Expanda **Dispositivos**.
3. Selecione **Provisionr novo dispositivo** na guia **Ações.**

Na janela **Provisionar novos dispositivos,** você pode adicionar o endereço MAC manualmente ou carregar um arquivo.

### <a name="manually-add-a-device-mac-address"></a>Adicionar manualmente um endereço MAC de dispositivo

1. Na guia **Aguardando ativação,** selecione **Adicionar ID MAC**.

   ![adicionar manualmente um endereço mac de dispositivo](../media/remote-provision-6.png)

1. Insira a ID MAC.
1. Insira um local, que ajuda os técnicos a identificar onde instalar os dispositivos.
1. Selecione **Aplicar** quando concluído.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Carregar um arquivo para adicionar um endereço MAC do dispositivo

1. Na guia **Aguardando ativação,** selecione **Carregar IDs MAC**.
2. Baixe o modelo de arquivo.
3. Insira a ID mac e o local e salve o arquivo.
4. **Selecione o arquivo** e selecione **Carregar**.

## <a name="generate-a-verification-code"></a>Gerar um código de verificação

Você precisa de um código de verificação para os dispositivos. O código de verificação é gerado em massa ou no nível do dispositivo e é válido por 24 horas.

1. Na guia **Aguardando ativação,** selecione uma ID MAC existente.
   Uma senha é criada para o endereço MAC e é mostrada na coluna **Código de** Verificação.

2. Forneça a lista de IDs MAC e códigos de verificação para os técnicos de campo. Você pode exportar os detalhes diretamente em um arquivo e compartilhar o arquivo com o técnico que está fazendo o trabalho de instalação real.

## <a name="provision-the-device"></a>Provisione o dispositivo

Quando o dispositivo é ligado e conectado à rede, o técnico provisiona o dispositivo. Essas etapas são concluídas no dispositivo Teams.

1. O técnico seleciona **Dispositivo de provisionamento** nas **Configurações**.  

   ![Provisione a nova opção de dispositivo na guia Ações](../media/provision-device1.png)
  
2. O técnico ins fornece o código de verificação específico do dispositivo no campo de entrada fornecido.

   ![Provisione a verificação de novo dispositivo](../media/provision-device-verification1.png)

   Depois que o dispositivo for provisionado com êxito, o nome do locatário será exibido na página de entrada.

   ![Nome do locatário na página de login](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Entrar remotamente

O dispositivo provisionado aparece na guia **Aguardando** entrada. Inicie o processo de entrada remota selecionando o dispositivo individual.

1. Selecione um dispositivo na guia **Aguardando entrada.**

   ![A janela com uma lista de dispositivos prontos para entrar.](../media/remote-device1.png)

2. Siga as instruções em **Entrar em um usuário** e selecione **Fechar**.

   ![a janela Entrar em um usuário para dispositivos individuais](../media/sign-in-user.png)

## <a name="related-article"></a>Artigo relacionado

- [Gerenciar seus dispositivos no Teams](device-management.md)
- [Atualizar dispositivos do Teams remotamente](remote-update.md)
