---
title: Suporte à migração da Unificação de Mensagens do Exchange Online
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: A Microsoft está retirando o serviço Exchange Unificação de Mensagens Online (ExchUMO) até 28 de fevereiro de 2020. Este artigo resume o que os clientes afetados devem saber e fazer para planejar a continuidade dos negócios.
ms.openlocfilehash: 1e6d24b05b8f1c6b8d2b47533edbd9ad79c5022e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013285"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte à migração da Unificação de Mensagens do Exchange Online

> [!IMPORTANT]
> **O serviço de Unificação de Mensagens Exchange Online está sem suporte a partir de 28 de fevereiro de 2020, 17:00 horas no Pacífico. Todas as contas de caixa postal foram migradas para Caixa postal na Nuvem serviço da Microsoft. Qualquer tráfego de atendimento automático restante não será monitorado e poderá ser interrompido a qualquer momento.**

Em referência [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) ao anúncio de 8 de fevereiro de 2019, a Microsoft está se retirando do serviço Exchange Unificação de Mensagens Online (ExchUMO) até 28 de fevereiro de 2020. Este artigo oferece um resumo do que os clientes afetados devem saber e fazer para planejar a continuidade dos negócios.

O ExchUMO é implantado pelos clientes para serviços de caixa postal, atendedor automático, Fila de Chamada e integração de fax. A Microsoft planeja ajudar os clientes a migrar para serviços Sistema de Telefonia que já suportam milhares de clientes no Skype for Business Online e Microsoft Teams.

A caixa postal é principalmente uma migração orientada pela Microsoft; envolvimento do administrador e/ou investimento pode ser necessário para um subconjunto de clientes. O atendimento automático é uma migração orientada pelo administrador; você precisará criar as árvores de atendimento automático do ExchUMO existentes no serviço de nuvem Atendedor Automático nuvem. Os clientes que consomem qualquer um dos recursos do ExchUMO com um PBX de terceiros não serão migrados para serviços de Skype de nuvem porque não suportam sistemas PBX de terceiros. Um plano de aposentadoria para suporte de terceiros foi anunciado neste [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)e os clientes nesse modelo de implantação podem migrar seus usuários para uma das plataformas/serviços de Comunicações Unificadas da Microsoft ou adquirir uma caixa postal de terceiros e/ou solução de atendedor automático para esses usuários. A integração de fax não é suportada nos serviços baseados em nuvem; os clientes precisarão migrar para uma solução de terceiros.

## <a name="who-is-affected"></a>Who é afetado?

Os clientes que usam qualquer um dos seguintes recursos do serviço Exchange Unificação de Mensagens Online são afetados:

- Serviço de caixa postal
- Atendedor Automático serviço
- Serviço fila de chamada
- Integração de fax

> [!Note]
> Os clientes que estão usando qualquer uma das Exchange Server local com a Unificação de Mensagens não são afetados.

Saiba mais sobre o impacto da experiência do usuário e do administrador no [impacto da experiência do usuário.](#user-experience-impact)

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e ajudarão os clientes a migrar com base no plano a seguir.

|Grupo de clientes |Linha do tempo  |Detalhes  |
|---------|---------|---------|
|Clientes que estão prontos para migrar<br><br>Recursos para migrar:<br><ul><li>Caixa postal</ul>   |   Março — maio de 2019  |Exemplos:<ul><li>    Clientes com implantação e uso simples de caixa postal<li>Clientes que têm todos os requisitos estabelecidos para a Microsoft executar a migração<ul>|
|Clientes com pré-requisitos<br><br>Recursos para migrar:<br><ul><li>Caixa postal<li>Atendedor automático<li>Fila de Chamada</ul> |  Maio — dezembro de 2019 |Exemplos: <br><ul><li>A configuração híbrida não está concluída<li>Os números PSTN híbridos não estão definidos</ul>|
|Clientes que exigem envolvimento do administrador & investimento do cliente<br><br>Recursos para migrar:<ul><li>voicemail<li>Atendedor automático<li>Filas de chamada<li>Integração de fax</ul>| Até fevereiro de 2020  | Exemplos: <br><ul><li>O serviço exchUMO é consumido pelo PBX de terceiros<li>Clientes com requisitos de Acesso para Assinante PSTN<li>Clientes no SFB 2010 (sem suporte)<li>Integração de fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Diretrizes de migração de caixa postal

### <a name="get-informed"></a>Obter informações

Familiarize-se com o [anúncio do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e este artigo para planejar uma migração suave para seus usuários. Consulte [Verificar Skype for Business caixa postal e opções](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os recursos Sistema de Telefonia Caixa Postal.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Estabelecer uma topologia Skype for Business híbrida

Se você não tiver uma topologia Skype for Business híbrida estabelecida, você precisará fazer isso para habilitar uma migração suave de seus usuários de caixa postal. Confira [Configurar Skype for Business híbrido para](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) obter mais detalhes.

> [!Note]
> Você não precisa migrar seus usuários online para a migração do serviço de caixa postal. No entanto, para que os usuários locais aproveitem Sistema de Telefonia caixa postal, uma topologia híbrida deve ser estabelecida.

### <a name="plan-your-auto-attendant-migration"></a>Planejar a migração do seu atendimento automático

Os administradores podem começar a migrar seus atendimentos automáticos do ExchUMO para o atendimento automático na nuvem a qualquer momento. Consulte [Configurar um assistente automático na nuvem](/microsoftteams/create-a-phone-system-auto-attendant) para obter mais detalhes.

A Microsoft continua a oferecer recursos adicionais de atendimento automático que os clientes podem considerar necessários para a migração. Os administradores devem avaliar o conjunto de recursos e migrar suas instâncias de atendimento automático de acordo. Para uma comparação de lista de recursos, consulte a matriz de recursos de serviços baseados em nuvem do [ExchUMO e do Azure.](#exchumo-and-azure-cloud-based-services-feature-matrix)

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planejar sua validação de caixa postal pós-migração e testes

A migração de caixa postal é orientada pela Microsoft. Os administradores não são obrigados a fazer nada, já que a topologia híbrida pré-requisito está estabelecida. A Microsoft executa a validação e os testes necessários para garantir que a migração da caixa postal dos usuários não seja interrompida. Os administradores são incentivados a realizar testes e validações do lado deles. Consulte [Plano de teste sugerido e validação pós-migração para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) para um plano de teste recomendado.

> [!Note]
> Não há suporte para o Lync Server 2010. Se você estiver em uma implantação de servidor 2010, planeje uma atualização de servidor ou considere migrar seus usuários para Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Monitorar o Centro de Notificação de Administrador

Observe um aviso na Central de Notificação de Administrador com mais detalhes e uma linha do tempo sobre a migração dos usuários. As notificações são enviadas pelo menos 30 dias antes do período de migração.

> [!Note]
> Se você recebeu uma notificação com a linha do tempo de migração dos usuários e gostaria de adiar sua migração por um motivo crítico para os negócios, você pode fazer isso contatando o Suporte da Microsoft. Você não pode adiar sua migração para além da data de aposentadoria de 28 de fevereiro de 2020. Para clientes que podem ter mais perguntas, entre em contato com sua equipe de conta ou suporte da Microsoft. Os clientes que já Microsoft 365 ou Office 365 podem enviar uma ocorrência de suporte por meio do Centro de administração do Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Considere a aceitação de uma migração planejada

Você pode optar por uma migração planejada do serviço de Caixa Postal para a CVM. Antes de optar, revise os detalhes deste artigo, especialmente as seções a seguir:

- Etapas de migração (esta seção)
- Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure
- Impacto da experiência do usuário

Ao escolher uma migração gerenciada, você não receberá uma notificação de 30 dias de pré-migração no Microsoft 365 de mensagens do portal de administração.

Para optar por uma migração planejada, envie uma solicitação de email do endereço de email do administrador para cvm@microsoft.com [com](mailto:cvm@microsoft.com) as seguintes informações:

- Data preferencial (terças-feiras): as ondas de migração são executadas todas as terças-feiras. Selecione uma data em uma terça-feira que não seja além de 3/12/2019.
 
- ID do locatário: número de 32 caracteres neste formato 0046728c-688a-4472-a38f-098fec60ac6x. Você pode encontrar sua ID de locatário no portal de administração do Microsoft 365 no Azure AD ou usando o seguinte cmdlet do PowerShell:`Get-CsTenant | Select ObjectId`

Você receberá uma confirmação de email depois que o locatário for migrado com êxito.

## <a name="auto-attendant-migration-guidelines"></a>Diretrizes de migração de atendimento automático

os administradores da organização do Microsoft 365 e do Office 365 são necessários para criar seus atendentes automáticos do UM Online do Exchange no serviço Microsoft Cloud Atendedor Automático e alternar seus números de telefone locais para eles antes da data de desligamento do serviço UMO do Exchange de 28 de fevereiro de 2020. Esta é a diretriz recomendada para migrar e testar com êxito novos atendentes automáticos na Nuvem. Se você tiver um grande número de atendimentos automáticos, poderá usar a Exchange um Atendedor Automático para [scripts](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) de migração de nuvem Atendedor Automático para simplificar a migração em massa de atendentes automáticos.

### <a name="auto-attendant-setup"></a>Configuração do atendedor automático

Recomendamos que você inicie a instalação dos novos atendentes automáticos mais cedo para evitar problemas de última hora e se familiarizar com a funcionalidade e a experiência do serviço de Atendedor Automático nuvem. Para os atendimentos automáticos que exigem um ou mais recursos de lacuna, você pode criar e testar os atendimentos automáticos quando os recursos de lacuna estão disponíveis para preparar a implantação. Para obter mais informações sobre recursos de lacuna, consulte [o Apêndice](#appendix).

1. Use os cmdlets Exchange UMO para exportar a configuração de atendentes automáticos existentes usando [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Use o cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) no Exchange Online PowerShell para exportar os arquivos de mídia de saudação (se usado) e convertê-los no formato .mp3.

3. Siga as instruções em [Plan Cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) and Set up a Cloud auto attendant to create auto [attendants](/microsoftteams/create-a-phone-system-auto-attendant) by using the Microsoft Teams admin center or PowerShell.

4. Revise suas saudações se as opções de menu foram alteradas.

5. Configure transferências para seus grupos de resposta usando a solução alternativa "transferência [](#known-issues) Atendedor Automático chamada para PSTN" na seção Problemas conhecidos deste artigo.  

6. Teste os novos atendentes automáticos chamando-os internamente ou atribuindo um número de telefone de teste.  

### <a name="cutover"></a>Substituição

1. Alternar seus números de telefone de Exchange de umo para os novos atendimentos automáticos.
2. Mova o URI SIP do objeto de contato para a conta de recurso.
3. Teste e valide seus atendimentos automáticos usando os números de telefone recém-atribuídos.

## <a name="appendix"></a>Apêndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure

| Serviço | Nível de recurso | Recurso | Observações  | VM/AA de nuvem  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Recursos de serviço| Suporte a PBX de terceiros    | Incluindo todos os recursos fornecidos para PBX de terceiros, como MWI (Indicador de Espera de Mensagens) usando mensagens de notificação SIP de Exchange UM Online | N   | Y    |
| VM | Recursos de serviço  | Suporte Skype for Business Server   |  | S | S    |
| VM | Recursos de serviço | Suporte Microsoft Teams|  | Y | N    |
| VM | Recursos de serviço | Descoberta EDiscovery e Hold  | Para segurança e conformidade  | S | S    |
| VM | Recursos de serviço | Exchange Suporte a regras | Para segurança e conformidade  | S | S    |
| VM | Recursos do usuário | Acesso discado PSTN  | Acesso ao assinante  | N | Y    |
| VM | Recursos do usuário | Delegar  | email de chamada perdida  | N | Y    |
| VM | Recursos do usuário | PSTN Outlook Voice Access   | Acesso ao assinante  | N | Y    |
| VM | Recursos do usuário | Discagem usando um ponto de extremidade autenticado | Chamar o serviço de caixa postal para ouvir mensagens de voz e alterar configurações de caixa postal| S | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a caixa postal   |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar a saudação pessoal  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para criar uma saudação OOF  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para substituir a saudação padrão com tTS  |  | Y | N    |
| VM | Recursos do usuário | Gravar saudações pessoais (dispositivo autenticado) |  | S | S    |
| VM | Recursos do usuário | Gravar saudações pessoais (PSTN) — tocar no telefone |  | N | Y    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a transcrição |  | N | Y    |
| VM | Recursos do usuário | Transcrição  |  | S | S    |
| VM | Recursos do usuário | MWI (Indicador de Espera de Mensagem) usando mensagens de notificação SIP |  | N | Y    |
| VM | Recursos do usuário | Formato de arquivo de áudio MP3 em Outlook    |  | S | S    |
| VM | Recursos do usuário | Controle de reprodução de velocidade variável |  | S | S    |
| VM | Recursos do usuário | Encaminhar uma caixa postal  | Encaminhar uma caixa postal recebida para outros usuários | S | S    |
| VM | Recursos do usuário | Enviando uma mensagem de voz para um grupo de usuários  |Transmissão de caixa postal   | N | Y   |
| VM | Recursos do usuário | Notificação de caixa postal usando SMS    | Os usuários podem receber um SMS quando têm uma nova caixa postal    | N | Y    |
| VM | Recursos do usuário | Idiomas de saudação com suporte | Detalhes aqui: [O que são os atendimentos automáticos na nuvem?](/microsoftteams/what-are-phone-system-auto-attendants) | S | S    |
| VM | Recursos do usuário | Regras de atendimento de chamada |  | S | S    |
| VM | Recursos do usuário | Tocar no telefone (PSTN)- para reproduzir mensagem | Chame-me no meu celular para ouvir a mensagem de voz  | N | Y    |
| VM | Recursos do usuário | Tocar no telefone (Auth)- para reproduzir mensagem | Chame-me no meu dispositivo autenticado  | N | Y    |
| VM | Recursos do usuário | Caixa de correio compartilhada entre vários usuários |  | S | S    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal protegida | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegida| N | Y    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal privada | O chamador pode escolher uma opção para marcar uma mensagem gravada como privada  | N | Y    |
| VM | Recursos do chamador  | Detecção de silêncio   |  | N | Y    |
| VM | Tenant-Admin recursos | Caixa postal protegida no nível do servidor    | O administrador de locatários pode configurar uma regra de nível de serviço para marcar a caixa postal de entrada como protegida | S | S    |
| VM | Tenant-Admin recursos | Alterar o limite de tempo de duração da gravação  |     | S | S    |
| VM | Tenant-Admin recursos | Alterar o tempo de detecção de silêncio    |  | N/D    | Y    |
| VM | Tenant-Admin recursos | Alterar o número de falhas de entrada | CVM: codificada para 3 | N | Y    |
| VM | Tenant-Admin recursos | Alterar o idioma padrão |  | S | S    |
| VM | Tenant-Admin recursos | Desabilitar/habilitar transcrição |  | S | S    |
| VM | Tenant-Admin recursos | Desabilitar/habilitar a notificação de chamada perdida |  | N | Y    |
| VM | Tenant-Admin recursos | Ajude a Microsoft a melhorar a visualização da caixa postal    |  | S | S    |
| VM | Tenant-Admin recursos | Personalizar mensagem de texto para usuários habilitados|  | N/D    | Y    |
| VM | Tenant-Admin recursos | Mascaramento de profanidade de transcrição|  | Y | N    |
| VM | Tenant-Admin recursos | Política de caixa postal    |   | S | S    |
| VM | Tenant-Admin recursos | Administração do portal da Web   |  | CY19   | Y    |
| VM | Tenant-Admin recursos | PowerShell   |  | S | S    |
| UM | Recursos do usuário | Indicador de Espera de Mensagem (MWI) em Skype for Business certificados   |Pode ser fornecido pelo parceiro de telefone  | Não | Sim    |
| AA | Recursos de serviço | AA support 3rd-party PBX    |  | N | Y    |
| AA | Recursos de serviço | Suporte Skype for Business Server   |  | S | S    |
| AA | Recursos de serviço | Suporte Microsoft Teams|  | Y | N    |
| AA | Recursos de serviço | Discar por nome, entrada DTMF    |  | S | S    |
| AA | Recursos de serviço | Discar por nome, entrada de fala  |  | S | S    |
| AA | Recursos de serviço | Suporte a vários idiomas | Detalhes do idioma aqui: [O que são os atendimentos automáticos na nuvem?](/microsoftteams/what-are-phone-system-auto-attendants) | S | S    |
| AA | Recursos de serviço | Transferir para operador, CQ ou usuário |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN internamente (DID RNL)  |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN externamente  |  | Confira a seção Problemas Conhecidos abaixo | Y    |
| AA | Recursos de serviço | Horário comercial |  | S | S    |
| AA | Recursos de serviço | Opções de menu | Opções de menu IVR  | S | S    |
| AA | Recursos de serviço | Atribuir um número PSTN de nuvem ao AA |  | Y | N    |
| AA | Recursos de serviço | Atribuindo um número PSTN ao AA  |  | S | S    |
| AA | Recursos de serviço | Seleção de usuário personalizada  | Habilitando os chamadores a alcançar a lista personalizada de usuários da organização| S | S    |
| AA | Recursos de serviço | Tratamento pós-horário e feriados  |  | S | S    |
| AA | Recursos de serviço | Saudação personalizada usando texto em fala  |  | S | S    |
| AA | Recursos de serviço | Discagem de ramal   | Alcançar um usuário discando sua extensão  | S   | S    |
| AA | Recursos de serviço | Caixa de correio para os chamadores AA deixarem uma mensagem    |  | S   | S    |
| AA | Recursos de serviço | Várias atribuições de número PSTN para um AA|  | S | S    |
| AA | Tenant-Admin recursos | Administração do portal da Web   |  | Y | N    |
| AA | Tenant-Admin recursos | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos de serviço | Integração de fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação pós-migração para administradores

Para validar se seus usuários foram migrados para Caixa postal na Nuvem, deixe uma caixa postal para um usuário e verifique o corpo da mensagem no Outlook. Caixa postal na Nuvem mensagens têm um rodapé que lê:

"Obrigado por usar Transcrição! Se você não vir uma transcrição acima, é porque a qualidade do áudio não foi clara o suficiente para transcrever."

Ao testar a funcionalidade da caixa postal após a migração dos usuários, considere os seguintes cenários:

- Valide o acesso à caixa postal em todos os tipos de ponto de extremidade em sua organização, como aplicativos e telefones IP.
- Valide com usuários de exemplo que as saudações personalizadas configuradas são tocadas para chamadores.
- Se sua organização tiver um requisito legal ou de conformidade para desabilitar a transcrição para usuários, certifique-se de que ela está desabilitada após a migração. Para obter mais detalhes, consulte [Configurar Caixa postal na Nuvem](/microsoftteams/set-up-phone-system-voicemail).
- Se você configurou anteriormente Exchange políticas e regras de VM, certifique-se de que elas sejam eficazes.
- Familiarize-se com os cmdlets Caixa postal na Nuvem serviço do PowerShell para alterar as configurações do usuário.  

### <a name="user-experience-impact"></a>Impacto da experiência do usuário

Veja a seguir uma visão geral da experiência de migração de caixa postal do usuário final.


|Experiência  |Alteração na experiência do usuário|
|---------|---------|
|Notificação de email | Sem alteração<br>Nenhum email é enviado aos usuários que os notificam sobre a ativação/migração da conta de caixa postal. |
|Acesso a mensagens anteriores | Sem alteração<br>Os usuários têm acesso às suas mensagens de voz anteriores em todos os pontos de extremidade suportados. |
|Recebimento de VM no Outlook, aplicativos SFB| Sem alteração<br>Os usuários continuam recebendo suas mensagens de caixa postal em todos os pontos de extremidade suportados. |
|Transcrição | Aprimorado<br>A transcrição da CVM tem uma taxa de precisão muito maior e idiomas com suporte do que o ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários podem alterar suas preferências de um Portal de Configuração do Usuário (USP). Os usuários podem acessar sua USP a partir de um hiperlink em seus emails de caixa postal ou o botão User-Settings no cliente SFB; https://aka.ms/vmsettings.
 |Recursos| Consulte a comparação de conjunto de recursos para obter detalhes. |
|Outlook regras para mensagens VM | Sem alteração<br>As regras criadas anteriormente serão aplicadas a mensagens DALL após a migração.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento e provisionamento de usuários na CVM

Os Skype for Business novos usuários serão provisionados automaticamente para a caixa postal na nuvem quando criados. Nenhum trabalho de administrador adicional ou licença é necessário para provisionar novos usuários de caixa postal. Consulte [Configurar um Caixa postal na Nuvem](/microsoftteams/set-up-phone-system-voicemail) para saber mais sobre o gerenciamento de políticas para usuários existentes e novos.

### <a name="admin-auto-attendant-management-experience"></a>Experiência de gerenciamento Atendedor Automático administrador

Para saber mais sobre os atendimentos automáticos, consulte [Configurar um atendimento automático na nuvem.](/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>Problemas conhecidos

#### <a name="greeting-inconsistencies"></a>Inconsistências de saudação

O acesso ao assinante pode continuar a funcionar para seu locatário até que o serviço seja completamente retirado, mesmo depois que todos os usuários foram migrados para Caixa postal na Nuvem. Para evitar confusão do usuário e uma experiência inconsistente, desabilite o acesso do assinante, pois as saudações mudam após a migração. Para fazer isso, remova o contato do EXUM para cada linha de acesso do assinante usando `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Atendedor Automático Transferência de Chamada para PSTN

Para transferir uma chamada de atendimento automático para um número de telefone PSTN externo via Skype for Business Server ou um serviço de Grupo de Resposta (RGS) no Skype for Business Server, crie um novo usuário local com encaminhamento de chamada definido para o número de telefone PSTN ou número de telefone RGS. O usuário deve estar habilitado e configurado corretamente para Enterprise Voice e ter uma política de voz atribuída.

#### <a name="shared-mailbox-is-still-accessible"></a>A caixa de correio compartilhada ainda está acessível

Uma caixa de correio compartilhada configurada usando Exchange UM Online continua a receber mensagens após a migração para a CVM e estar acessível aos usuários por meio Outlook. No entanto, o acesso para alterar as mensagens de saudação dessas caixas de correio não estará disponível depois de migrado para a CVM. Os clientes com caixas de correio compartilhadas usadas para capturar chamadores de atendimento automático devem aproveitar os recursos de Caixa de Correio Compartilhada de Filas de Chamada e Atendimento Automático depois de lançado (ETA outubro de 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>O banner "Username is not using Skype for Business" é exibido

O serviço DALS baseia-se na infraestrutura de Microsoft Teams, e as chamadas de um cliente Skype for Business podem fazer com que um banner de informações seja exibido no cliente que diz: "Nome de usuário não está usando Skype for Business. Para uma experiência mais rica, alternar para Teams ou iniciar uma Skype reunião."
Certifique-se de atualizar o cliente Skype for Business cliente de seus usuários para a atualização mais recente do cliente C2R para impedir que essa faixa apareça.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurar Caixa Postal" leva você ao OWA

Clicar  em Configurar Caixa Postal do cliente continuará levando os clientes Skype for Business Server 2015/2013 para a página do portal do Office Web Access (OWA) após a migração para a CVM. Todas as configurações foram removidas da guia Caixa Postal no OWA e uma faixa será exibida com um link de redirecionamento para levar os usuários ao portal de configurações do usuário da CVM.

#### <a name="changing-greeting-remotely"></a>Alterando a saudação remotamente

O acesso ao assinante PSTN não é suportado na CVM. Para usuários que precisam alterar suas saudações remotamente, uma opção de menu "Alterar sua saudação" foi adicionada ao serviço IVR da caixa postal para clientes móveis. Os usuários podem chamar esse serviço pressionando e segurando a tecla "1" no teclado de discagem do cliente móvel.