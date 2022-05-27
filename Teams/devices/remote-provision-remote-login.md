---
title: Provisionamento remoto e entrada para Teams Android dispositivos
author: cazawideh
ms.author: czawideh
manager: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como provisionar e entrar remotamente para dispositivos Teams Android remotos
ms.openlocfilehash: 4b3831bc42da92939c7aa61ff52a15266dc4a940
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674333"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Provisionamento remoto e entrada para Teams Android dispositivos

Os administradores de TI podem provisionar e entrar remotamente em um Teams Android dispositivo. Para provisionar um dispositivo remotamente, o administrador precisa carregar as IDs MAC dos dispositivos que estão sendo provisionados e criar um código de verificação. Todo o processo pode ser concluído remotamente no centro Teams administrador.

## <a name="review-the-supported-devices"></a>Examinar os dispositivos com suporte

A lista a seguir mostra os requisitos Android firmware do dispositivo.

|Categoria de dispositivo|Modelo de dispositivo|Versão do firmware|
|---|---|---|
|Teams telefone|Yealink T55/T56/T58|58.15.0.124|
|Teams telefone|Yealink VP59|91.15.0.58|
|Teams telefone|Yealink CP960|73.15.0.117|
|Teams telefone|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams telefone|Crestron UC-2|1.0.3.52|
|Teams telefone|Poly Trio C60|7.0.2.1071|
|Teams telefone|CCX400/CCX500/CCX600 |7.0.2.1072|
|Teams telefone|Códigos de áudio C448HD/C450HD/C470HD|1.10.120|
|Teams painéis|Crestron 770/1070|1.004.0115|
|Salas do Teams no Android|Logitech Rally Bar Mini|1.2.982|
|Salas do Teams no Android|Logitech Rally Bar|1.2.982|
|Salas do Teams no Android|AudioCodes RXV80|1.13.361|
|Salas do Teams no Android|EPOS EXPAND Vision 3T|1.2.2.21182.10|
|Salas do Teams no Android|Yealink MeetingBar A30|133.15.0.60|
|Salas do Teams no Android|Yealink MeetingBar A20|133.15.0.60|
|Salas do Teams no Android|Console de toque yealink CTP18|137.15.0.37|
|Salas do Teams no Android|Poly Studio X30|3.5.0.344025|
|Salas do Teams no Android|Poly Studio X50|3.5.0.344025|
|Salas do Teams no Android|Console de toque poly TC8 |3.5.0.210489|
|Salas do Teams no Android|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>Adicionar um endereço MAC do dispositivo

Conclua as etapas a seguir para provisionar um novo dispositivo.

1. Entre no Centro de administração do Teams.
2. **Expanda Teams dispositivos**.
3. Selecione **Provisionar novo dispositivo** na **guia** Ações.

Na janela **Provisionar novos** dispositivos, você pode adicionar o endereço MAC manualmente ou carregar um arquivo.

### <a name="manually-add-a-device-mac-address"></a>Adicionar manualmente um endereço MAC do dispositivo

1. Na guia **Aguardando na ativação** , selecione **Adicionar ID do MAC**.

   ![adicionar manualmente um endereço mac do dispositivo.](../media/remote-provision-6-new.png)

1. Insira a ID do MAC.
1. Insira um local, que ajuda os técnicos a identificar onde instalar os dispositivos.
1. Selecione **Aplicar** quando terminar.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Upload um arquivo para adicionar um endereço MAC do dispositivo

1. Na guia **Aguardando na ativação**, selecione **Upload IDs do MAC**.
2. Baixe o modelo de arquivo.
3. Insira a ID e o local do MAC e salve o arquivo.
4. **Selecione o arquivo** e selecione **Upload**.

## <a name="generate-a-verification-code"></a>Gerar um código de verificação

Você precisa de um código de verificação para os dispositivos. O código de verificação é gerado em massa ou no nível do dispositivo e é válido por 24 horas.

1. Na guia **Aguardando na ativação** , selecione uma ID mac existente.
   Uma senha é criada para o endereço MAC e é mostrada na coluna **Código de** Verificação.

2. Forneça a lista de IDs MAC e códigos de verificação para os técnicos de campo. Você pode exportar os detalhes diretamente em um arquivo e compartilhar o arquivo com o técnico que está fazendo o trabalho de instalação real.

## <a name="provision-the-device"></a>Provisionar o dispositivo

Quando o dispositivo está ligado e conectado à rede, o técnico provisiona o dispositivo. Essas etapas são concluídas no Teams dispositivo.

1. O técnico seleciona **Provisionar dispositivo** na **Configurações**.  

   ![Provisione a nova opção de dispositivo na guia Ações.](../media/provision-device1.png)
  
2. O técnico insere o código de verificação específico do dispositivo no campo de entrada fornecido.

   ![Provisione a nova verificação de dispositivo.](../media/provision-device-verification1.png)

   Depois que o dispositivo for provisionado com êxito, o nome do locatário aparecerá na página de entrada.

   ![Nome do locatário na página de entrada.](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>Primeira vez que você entra remotamente

O dispositivo provisionado aparece na **guia Aguardando entrada** . Inicie o processo de entrada remota selecionando o dispositivo individual.

1. Selecione um dispositivo na **guia Aguardando** entrada.

   ![A janela com uma lista de dispositivos prontos para entrar.](../media/remote-device1.png)

2. Siga as instruções em **Conectar um usuário** e, em seguida, selecione **Fechar**.

   ![a janela Entrar em um usuário para um dispositivo individual.](../media/sign-in-user.png)

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar seus dispositivos no Teams](device-management.md)
- [Entrar e sair remotamente](remote-sign-in-and-sign-out.md)
- [Atualizar Teams dispositivos remotamente](remote-update.md)
