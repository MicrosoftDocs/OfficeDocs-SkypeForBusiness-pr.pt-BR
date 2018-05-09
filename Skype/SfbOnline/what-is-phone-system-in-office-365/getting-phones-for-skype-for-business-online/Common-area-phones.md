---
title: Implantar telefones para o Skype for Business Online
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a>Telefones de área comum
Um telefone de área comum ou COBRIR, é geralmente colocada em uma área compartilhada e não associado a um usuário individual. Por exemplo, um telefone de área de recepção, porta telefone ou sala de reunião telefone, maiusculas são configuradas como dispositivos em vez de usuários e entrar automaticamente à rede. Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema de telefone da Microsoft com planos de chamada e, em seguida, implantar uma Capitular.

## <a name="prerequisites-for-common-area-phones"></a>Pré-requisitos para telefones de área comum

Confirme que você tenha o seguinte:

    - Adquirido SKU do telefone de área comum 
    - (Consulte suporte Firmware tópico do firmware atualizadohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
    - Telefones aprovadas (exibir a lista nohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones) 


## <a name="check-the-firmware-for-your-phone"></a>Verifique o firmware para o seu telefone
- **Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.
- **Telefones Yealink**, vá para **Status** na tela do telefone principal.
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen. 
- **Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.

As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. 

Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes. Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ para `false`.

## <a name="create-cap"></a>Criar COBRIR
Você pode criar o COBRIR definindo as configurações antes de configurar o telefone físico.

#### <a name="purchase-the-common-area-phone-sku"></a>Adquira o telefone de área comum SKU. 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>Configurar o telefone de área comum<!-- this section could use a screen shot-->

**Criar um usuário** 
1. Atribuir um telefone de área comum SKU
2. Atribua chamar planejar (se estiver usando o sistema de telefone da Microsoft com planos de chamada). 
3. Atribuir um número de telefone disponíveis no Skype para Business Admin Center, ou solicitar um novo número de telefone.

**Criar um novo usuário**

1. No painel de provisionamento, você tem uma opção para digitar um nome e sobrenome (por exemplo, Main de recepção).
2. Insira um nome para exibição (obrigatório), por exemplo, "Main recepção."
3. Insira um nome de usuário (obrigatório), por exemplo "MainReception" @"domínio" (nome de empresa ou enterprise)
4. Insira o local (país).

**Atribuir um telefone de área comum SKU** No Centro de administração do Office 365, vá para **faturamento > Serviços de compra** e adicione o **Telefone de área comum**

**Atribuir o plano de chamada no COBRIR SKU**

1. Selecione uma chamada planeja habilitar o telefone. 
2. Adicione o limite para permitir que o sistema telefônico e Skype para negócios Online plano 2 na SKU COBRIR. <!-- odd order for step -->

**Atribuir um número de telefone**
1. Verificar números de telefone disponíveis em **voz > números de telefone**.
2. Selecione um número na lista disponível do número de números de telefone.
3. Confirme sua seleção selecionando os **Números de telefone**e **voz** .

    >[Nota] Usuários de voz mostram somente se tiverem a licença do sistema telefônico aplicada, embora o mesmo depois de aplicar, poderá demorar para ser atualizada. Reabrir um dia Skype para Business Admin center ajuda.
    
## <a name="configure-phone"></a>Configurar o telefone

**Preparar os telefones físicos** 

Seu telefone selecionado precisa ter o modo de telefone de área comum. 

***Telefone de Polycom VVX de exemplo***

Habilite o modo do telefone de área comum em Polycom VVX seguindo estas etapas:
1. No seu navegador, use a interface da web para habilitar o modo de COBRIR o VVX
2. Vá para **configuração** e no Skype para a opção de configuração de negócios, selecione o **Telefone de área comum**.
3. Clique em **Salvar** para salvar as suas definições de configuração.

Agora que o modo de telefone COBRIR estiver habilitado, configure o telefone usando a exibição do telefone.

1. Nas configurações, selecione **Avançado**.
2. Insira a senha.
3. Nas configurações de administração, selecione **Configurações de telefone de área comum**.
4. Habilitar o Common Area Phone and COBRIR Admin
5. Selecione **Salvar o arquivo Config**.

Seu telefone está pronto para ser provisionados, o qual você vai fazer quando você entrar na tela inicial.

1. Entrar selecionando **Configurações > recursos > Skype for Business.**
2. Selecione as credenciais do usuário e, em seguida, selecione selecionar **entrar na web (COBRIR)** para gerar um código..
3. Vá para o portal de provisionamento http://aka.ms/skypecape entrar como **admin**.
4. Insira o nome de exibição (por exemplo, Main recepção) para exibir seu limite.

>[Nota] Se "Pesquisa para telefones de área comum apenas" estiver marcada, desmarque a caixa de seleção e pesquisar novamente.

5. Na janela de código de emparelhamento, insira o código exibido no telefone e clique em **fornecimento**.

WHT essa última etapa, o telefone deve entrar automaticamente.

Saiba mais sobre os telefones disponíveis em [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).


