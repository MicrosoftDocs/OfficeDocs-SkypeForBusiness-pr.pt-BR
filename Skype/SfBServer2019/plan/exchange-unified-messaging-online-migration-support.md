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
localization_priority: Normal
description: A Microsoft está retirando o serviço Exchange Unified Messaging Online (ExchUMO) até 28 de fevereiro de 2020. Este artigo resume o que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.
ms.openlocfilehash: 5ee0cb6329f03c5306d14603ab9beedfd8ed55da
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177421"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte à migração da Unificação de Mensagens do Exchange Online

> [!IMPORTANT]
> **O serviço de Unificação de Mensagens no Exchange Online está sem suporte a partir de 28 de fevereiro de 2020, às 17h, horário do Pacífico. Todas as contas de caixa postal foram migradas para o serviço de Caixa Postal na Nuvem pela Microsoft. Qualquer tráfego de atendimento automático restante não será monitorado e poderá ser interrompido a qualquer momento.**

Em referência [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) ao comunicado de 8 de fevereiro de 2019, a Microsoft está retirando o serviço Exchange Unified Messaging Online (ExchUMO) até 28 de fevereiro de 2020. Este artigo oferece um resumo do que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.

O ExchUMO é implantado pelos clientes para serviços de caixa postal, atendedor automático, Fila de Chamada e integração de fax. A Microsoft planeja ajudar os clientes a migrar para serviços do Sistema de Telefonia que já suportam milhares de clientes no Skype for Business Online e no Microsoft Teams.

A caixa postal é principalmente uma migração orientada pela Microsoft; o envolvimento do administrador e/ou o investimento podem ser necessários para um subconjunto de clientes. O atendimento automático é uma migração orientada pelo administrador; será necessário criar as árvores existentes do atendente automático ExchUMO no serviço de nuvem do Atendente Automático na Nuvem. Os clientes que consomem qualquer um dos recursos exchUMO com um PBX de terceiros não serão migrados para os serviços de nuvem do Skype porque não suportam sistemas PBX de terceiros. Um plano de desuso para suporte de terceiros foi anunciado neste [blog,](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)e os clientes nesse modelo de implantação podem migrar seus usuários para uma das plataformas/serviços de Comunicações Unificadas da Microsoft ou adquirir uma caixa postal de terceiros e/ou solução de atendedor automático para esses usuários. A integração de fax não é suportada nos serviços baseados em nuvem; os clientes precisarão migrar para uma solução de terceiros.

## <a name="who-is-affected"></a>Quem é afetado?

Os clientes que usam qualquer um dos seguintes recursos do serviço de Unificação de Mensagens do Exchange Online são afetados:

- Serviço de caixa postal
- Serviço De atendimento automático
- Serviço de fila de chamada
- Integração de fax

> [!Note]
> Os clientes que estão usando qualquer um dos Exchange Server local com a Unificação de Mensagens não são afetados.

Saiba mais sobre o impacto da experiência do usuário e do administrador no [impacto da experiência do usuário.](#user-experience-impact)

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e ajudarão os clientes a migrar com base no plano a seguir.

|Grupo de clientes |Linha do tempo  |Detalhes  |
|---------|---------|---------|
|Clientes que estão prontos para migrar<br><br>Recursos para migrar:<br><ul><li>Caixa postal</ul>   |   Março – maio de 2019  |Exemplos:<ul><li>    Clientes com implantação e uso de caixa postal simples<li>Clientes com todos os requisitos estabelecidos para que a Microsoft execute a migração<ul>|
|Clientes com pré-requisitos<br><br>Recursos para migrar:<br><ul><li>Caixa postal<li>Auto attendant<li>Fila de chamada</ul> |  Maio – dezembro de 2019 |Exemplos: <br><ul><li>A configuração híbrida não foi concluída<li>Os números PSTN híbridos não estão definidos</ul>|
|Clientes que exigem envolvimento do administrador & investimento do cliente<br><br>Recursos para migrar:<ul><li>voicemail<li>Auto attendant<li>Filas de chamada<li>Integração de fax</ul>| Até fevereiro de 2020  | Exemplos: <br><ul><li>O serviço ExchUMO é consumido por PBX de terceiros<li>Clientes com requisitos de Acesso de Assinante PSTN<li>Clientes no SFB 2010 (sem suporte)<li>Integração de fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Diretrizes de migração de caixa postal

### <a name="get-informed"></a>Obter informado

Familiarize-se com o [anúncio do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e com este artigo para planejar uma migração suave para seus usuários. Consulte [a caixa postal do Skype for Business e as opções](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os recursos de Caixa Postal do Sistema de Telefonia.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Estabelecer uma topologia híbrida do Skype for Business

Se você não tiver uma topologia híbrida do Skype for Business estabelecida, precisará fazer isso para habilitar uma migração suave dos usuários da caixa postal. Confira [Configurar o Skype for Business híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obter mais detalhes.

> [!Note]
> Você não precisa migrar seus usuários online para a migração do serviço de caixa postal. No entanto, para que os usuários locais aproveitem o serviço de caixa postal do Sistema de Telefonia, uma topologia híbrida deve ser estabelecida.

### <a name="plan-your-auto-attendant-migration"></a>Planejar a migração do seu atendente automático

Os administradores podem começar a migrar seus atendentes automáticos do ExchUMO para o atendente automático do Cloud a qualquer momento. Consulte [Configurar um atendente automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para obter mais detalhes.

A Microsoft continua a oferecer recursos adicionais de atendimento automático que os clientes podem considerar necessários para sua migração. Os administradores devem avaliar o conjunto de recursos e migrar as instâncias do seu atendente automático de acordo. Para ver uma comparação de lista de recursos, confira a matriz de recursos de serviços baseados em nuvem [do ExchUMO](#exchumo-and-azure-cloud-based-services-feature-matrix)e do Azure.

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planejar sua validação e teste pós-migração da caixa postal

A migração da caixa postal é controlada pela Microsoft. Os administradores não precisam fazer nada, já que a topologia híbrida de pré-requisito é estabelecida. A Microsoft realiza a validação e os testes necessários para garantir que a migração da caixa postal dos usuários não seja interrompida. Os administradores são incentivados a executar testes e validação do lado deles. Consulte [Plano de teste sugerido e validação pós-migração para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) de um plano de teste recomendado.

> [!Note]
> Não há suporte para o Lync Server 2010. Se você estiver em uma implantação de servidor de 2010, planeje uma atualização de servidor ou considere migrar seus usuários para o Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Monitorar o Centro de Notificação de Administrador

Assista a um aviso no Centro de Notificações do Administrador com mais detalhes e uma linha do tempo sobre a migração dos usuários. As notificações são enviadas pelo menos 30 dias antes do período de migração.

> [!Note]
> Se você recebeu uma notificação com a linha do tempo de migração dos usuários e gostaria de adiar a migração por um motivo crítico para os negócios, entre em contato com o Suporte da Microsoft. Você não pode adiar sua migração além da data de baixa de 28 de fevereiro de 2020. Para clientes que possam ter mais perguntas, entre em contato com sua equipe de conta ou com o Suporte da Microsoft. Os clientes que já usam o Microsoft 365 ou o Office 365 podem enviar um caso de suporte por meio do Centro de administração do Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Considere a aceitação de uma migração planejada

Você pode optar por uma migração planejada do serviço de Caixa Postal para o SETOR. Antes de optar por isso, revise os detalhes deste artigo, especialmente as seções a seguir:

- Etapas de migração (esta seção)
- Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure
- Impacto na experiência do usuário

Ao escolher uma migração gerenciada, você não receberá uma notificação de pré-migração de 30 dias no centro de mensagens do portal de administração do Microsoft 365.

Para optar por uma migração planejada, envie uma solicitação de email do endereço de email do administrador para cvm@microsoft.com [as](mailto:cvm@microsoft.com) seguintes informações:

- Data preferencial (terças-feiras): as ondas de migração são executadas todas as terças-feiras. Selecione uma data em uma terça-feira que não ultrapassar 3/12/2019.
 
- ID do locatário: número de 32 caracteres neste formato 0046728c-688a-4472-a38f-098fec60ac6x. Você pode encontrar sua ID de locatário no portal de administração do Microsoft 365 no Azure AD ou usando o seguinte cmdlet do PowerShell: `Get-CsTenant | Select ObjectId`

Você receberá uma confirmação por email depois que seu locatário for migrado com êxito.

## <a name="auto-attendant-migration-guidelines"></a>Diretrizes de migração do atendente automático

Os administradores da organização do Microsoft 365 e do Office 365 devem re-criar seus participantes automáticos do UM Online do Exchange no serviço Microsoft Cloud Auto Attendant e alternar seus números de telefone locais para eles antes da data de desabilitação do serviço UMO do Exchange de 28 de fevereiro de 2020. Esta é a diretriz recomendada para migrar e testar com êxito novos participantes automáticos da nuvem. Se você tiver um grande número de atendimentos automáticos, poderá usar os [scripts](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) Do Atendente Automático do UM do Exchange para Migração do Atendente Automático na Nuvem para simplificar a migração em massa de atendentes automáticos.

### <a name="auto-attendant-setup"></a>Configuração do atendedor automático

Recomendamos que você inicie a configuração dos novos participantes automáticos mais cedo para evitar problemas de último minuto e se familiarizar com a funcionalidade e a experiência do serviço De atendimento automático na nuvem. Para os atendentes automáticos que exigem um ou mais recursos de lacuna, você pode criar e testar os atendentes automáticos quando os recursos do intervalo estão disponíveis para preparar a implantação. Para obter mais informações sobre recursos de lacunas, consulte o [Apêndice.](#appendix)

1. Use os cmdlets umO do Exchange para exportar a configuração de atendentes automáticos existentes usando [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Use o cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) no PowerShell do Exchange Online para exportar os arquivos de mídia de saudação (se usado) e convertê-los no formato .mp3.
3. Siga as instruções em [Plan Cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) and [Set up a Cloud auto attendants](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) to create auto attendants by using the Microsoft Teams admin center or Powershell.
4. Revise suas saudações se as opções do menu foram alteradas.
5. Configure transferências para seus grupos de resposta usando a solução alternativa "Transferência de Chamada do Atendente Automático para PSTN" na seção Problemas conhecidos deste artigo. [](#known-issues)  
6. Teste os novos atendentes automáticos chamando-os internamente ou atribuindo um número de telefone de teste.  

### <a name="cutover"></a>Substituição

1. Alternar seus números de telefone dos participantes automáticos da UMO do Exchange para os novos participantes automáticos.
2. Mova o URI do SIP do objeto de contato para a conta de recurso.
3. Teste e valide seus atendentes automáticos usando os números de telefone atribuídos recentemente.

## <a name="appendix"></a>Apêndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure

| Serviço | Nível de recursos | Recurso | Observações  | VM/AA de nuvem  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Recursos de serviço| Suporte a PBX de terceiros    | Incluindo todos os recursos fornecidos para PBX de terceiros, como MWI (Indicador de Espera de Mensagem) usando mensagens de notificação SIP do Exchange UM Online | N   | S    |
| VM | Recursos de serviço  | Suporte do Skype for Business Server   |  | S | S    |
| VM | Recursos de serviço | Suporte ao Microsoft Teams|  | S | N    |
| VM | Recursos de serviço | Descoberta e Espera  | Para segurança e conformidade  | S | S    |
| VM | Recursos de serviço | Suporte a regras do Exchange | Para segurança e conformidade  | S | S    |
| VM | Recursos do usuário | Acesso de discagem PSTN  | Acesso de assinante  | N | S    |
| VM | Recursos do usuário | Delegar  | email de chamada perdida  | N | S    |
| VM | Recursos do usuário | PSTN Outlook Voice Access   | Acesso de assinante  | N | S    |
| VM | Recursos do usuário | Discagem usando um ponto de extremidade autenticado | Chamar o serviço de caixa postal para ouvir mensagens de voz e alterar as configurações de caixa postal| S | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a caixa postal   |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar a saudação pessoal  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para criar uma saudação de OOF  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para substituir a saudação padrão com TTS  |  | S | N    |
| VM | Recursos do usuário | Gravar saudações pessoais (dispositivo autenticado) |  | S | S    |
| VM | Recursos do usuário | Gravar saudações pessoais (PSTN) — tocar no telefone |  | N | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a transcrição |  | N | S    |
| VM | Recursos do usuário | Transcrição  |  | S | S    |
| VM | Recursos do usuário | MWI (Indicador de Espera de Mensagem) usando mensagens de notificação SIP |  | N | S    |
| VM | Recursos do usuário | Formato de arquivo de áudio MP3 no Outlook    |  | S | S    |
| VM | Recursos do usuário | Controle de reprodução de velocidade variável |  | S | S    |
| VM | Recursos do usuário | Encaminhar uma caixa postal  | Encaminhar uma caixa postal recebida para outros usuários | S | S    |
| VM | Recursos do usuário | Enviar uma mensagem de voz para um grupo de usuários  |Transmissão de caixa postal   | N | S   |
| VM | Recursos do usuário | Notificação de caixa postal usando SMS    | Os usuários podem receber um SMS quando têm uma nova caixa postal    | N | S    |
| VM | Recursos do usuário | Idiomas de saudação com suporte | Detalhes aqui: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| VM | Recursos do usuário | Regras de atendimento de chamada |  | S | S    |
| VM | Recursos do usuário | Tocar no telefone (PSTN)- para reproduzir mensagem | Ligue-me na minha célula para ouvir a mensagem de voz  | N | S    |
| VM | Recursos do usuário | Tocar no telefone (Auth)- para reproduzir mensagem | Ligue-me em meu dispositivo autenticado  | N | S    |
| VM | Recursos do usuário | Caixa de correio compartilhada entre vários usuários |  | S | S    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal protegida | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegida| N | S    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal privada | O chamador pode escolher uma opção para marcar uma mensagem gravada como privada  | N | S    |
| VM | Recursos do chamador  | Detecção de silêncio   |  | N | S    |
| VM | Tenant-Admin recursos | Caixa postal protegida no nível do servidor    | O administrador de locatários pode configurar uma regra de nível de serviço para marcar a caixa postal de entrada como protegida | S | S    |
| VM | Tenant-Admin recursos | Alterar o limite de tempo de duração do registro  |     | S | S    |
| VM | Tenant-Admin recursos | Alterar o tempo de detecção de silêncio    |  | N/D    | S    |
| VM | Tenant-Admin recursos | Alterar o número de falhas de entrada | ACORDO: codificado como 3 | N | S    |
| VM | Tenant-Admin recursos | Alterar o idioma padrão |  | S | S    |
| VM | Tenant-Admin recursos | Desabilitar/habilitar transcrição |  | S | S    |
| VM | Tenant-Admin recursos | Desabilitar/habilitar notificação de chamada perdida |  | N | S    |
| VM | Tenant-Admin recursos | Ajude a Microsoft a melhorar a visualização da caixa postal    |  | S | S    |
| VM | Tenant-Admin recursos | Personalizar mensagem de texto para usuários habilitados|  | N/D    | S    |
| VM | Tenant-Admin recursos | Mascaramento de obsceção|  | S | N    |
| VM | Tenant-Admin recursos | Política de caixa postal    |   | S | S    |
| VM | Tenant-Admin recursos | Administração do portal da Web   |  | CY19   | S    |
| VM | Tenant-Admin recursos | PowerShell   |  | S | S    |
| UM | Recursos do usuário | Indicador de Espera de Mensagem (MWI) em telefones certificados pelo Skype for Business   |Pode ser fornecido por um parceiro de telefone  | Não | Sim    |
| AA | Recursos de serviço | AA support 3rd-party PBX    |  | N | S    |
| AA | Recursos de serviço | Suporte do Skype for Business Server   |  | S | S    |
| AA | Recursos de serviço | Suporte ao Microsoft Teams|  | S | N    |
| AA | Recursos de serviço | Discagem por nome, entrada DTMF    |  | S | S    |
| AA | Recursos de serviço | Discar por nome, entrada de fala  |  | S | S    |
| AA | Recursos de serviço | Suporte a vários idiomas | Detalhes do idioma aqui: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| AA | Recursos de serviço | Transferir para operador, CQ ou usuário |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN internamente (DID RNL)  |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN externamente  |  | Confira a seção Problemas Conhecidos abaixo | S    |
| AA | Recursos de serviço | Horário comercial |  | S | S    |
| AA | Recursos de serviço | Opções de menu | Opções do menu IVR  | S | S    |
| AA | Recursos de serviço | Atribuindo um número PSTN de nuvem ao AA |  | S | N    |
| AA | Recursos de serviço | Atribuindo um número PSTN no lugar ao AA  |  | S | S    |
| AA | Recursos de serviço | Seleção de usuário personalizada  | Permitindo que os chamadores alcancem uma lista personalizada de usuários da organização| S | S    |
| AA | Recursos de serviço | Tratamento de horas extras e feriados  |  | S | S    |
| AA | Recursos de serviço | Saudação personalizada usando texto em fala  |  | S | S    |
| AA | Recursos de serviço | Discagem de ramal   | Alcançar um usuário discando sua extensão  | S   | S    |
| AA | Recursos de serviço | Caixa de correio para chamadores AA deixarem uma mensagem    |  | S   | S    |
| AA | Recursos de serviço | Várias atribuições de número PSTN para um AA|  | S | S    |
| AA | Tenant-Admin recursos | Administração do portal da Web   |  | S | N    |
| AA | Tenant-Admin recursos | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos de serviço | Integração de fax|  | N | S    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação pós-migração para administradores

Para validar se os usuários foram migrados para a Caixa Postal na Nuvem, deixe uma caixa postal para um usuário e verifique o corpo da mensagem no Outlook. As mensagens de caixa postal na nuvem têm um rodapé que lê:

"Obrigado por usar a Transcrição! Se você não vir uma transcrição acima, é porque a qualidade do áudio não foi clara o suficiente para transcrever."

Ao testar a funcionalidade da caixa postal após a migração dos usuários, considere os seguintes cenários:

- Valide o acesso à caixa postal em todos os tipos de ponto de extremidade em sua organização, como aplicativos e telefones IP.
- Valide com exemplos de usuários que as saudações personalizadas configuradas são tocadas para chamadores.
- Se a sua organização tiver um requisito legal ou de conformidade para desabilitar a transcrição para os usuários, certifique-se de que ela está desabilitada após a migração. Para obter mais detalhes, consulte [Configurar caixa postal na nuvem.](/microsoftteams/set-up-phone-system-voicemail)
- Se você configurou políticas e regras de VM do Exchange anteriormente, certifique-se de que elas sejam eficazes.
- Familiarize-se com os cmdlets do PowerShell do serviço de Caixa Postal na Nuvem para alterar as configurações do usuário.  

### <a name="user-experience-impact"></a>Impacto na experiência do usuário

A seguir está uma visão geral da experiência de migração de caixa postal do usuário final.


|Experiência  |Mudança na experiência do usuário|
|---------|---------|
|Notificação por email | Sem alteração<br>Nenhum email é enviado aos usuários notificando-os sobre a ativação/migração da conta de caixa postal. |
|Acesso a mensagens anteriores | Sem alteração<br>Os usuários têm acesso às mensagens de caixa postal anteriores em todos os pontos de extremidade suportados. |
|Recebendo VM no Outlook, aplicativos SFB| Sem alteração<br>Os usuários continuam recebendo suas mensagens de caixa postal em todos os pontos de extremidade suportados. |
|Transcrição | Enhanced<br>A transcrição DACO tem uma taxa de precisão muito maior e idiomas com suporte do que ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários podem alterar suas preferências de um Portal de Configuração do Usuário (PORTAL DE CONFIGURAÇÃO do Usuário). Os usuários podem acessar seu CASO a partir de um hiperlink em seus emails de caixa postal ou o botão User-Settings no cliente SFB; https://aka.ms/vmsettings.
 |Recursos| Consulte a comparação do conjunto de recursos para obter detalhes. |
|Regras do Outlook para mensagens de VM | Sem alteração<br>As regras criadas anteriormente serão aplicadas às mensagens DOLS após a migração.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento de usuários e provisionamento noDA

Novos usuários do Skype for Business serão provisionados automaticamente para caixa postal na nuvem quando criados. Nenhum trabalho ou licença adicional do administrador é necessário para provisionar novos usuários de caixa postal. Consulte [Configurar a Caixa Postal na](/microsoftteams/set-up-phone-system-voicemail) Nuvem para saber mais sobre o gerenciamento de políticas para usuários novos e existentes.

### <a name="admin-auto-attendant-management-experience"></a>Experiência de gerenciamento do Assistente Automático de Administração

Para saber mais sobre os atendentes automáticos, consulte [Configurar um atendente automático na nuvem.](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>Problemas conhecidos

#### <a name="greeting-inconsistencies"></a>Inconsistências de saudação

O acesso do assinante pode continuar a funcionar para seu locatário até que o serviço seja completamente retirado, mesmo depois que todos os usuários foram migrados para a Caixa Postal na Nuvem. Para evitar confusão para o usuário e uma experiência inconsistente, desabilite o acesso do assinante, pois as saudações mudam após a migração. Para fazer isso, remova o contato EXUM de cada linha de acesso do assinante usando `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Transferência de Chamada de Atendimento Automático para PSTN

Para transferir uma chamada de atendimento automático para um número de telefone PSTN externo via Skype for Business Server ou um serviço de Grupo de Resposta (RGS) no Skype for Business Server, crie um novo usuário local com encaminhamento de chamada definido para o número de telefone PSTN ou número de telefone RGS. O usuário deve estar habilitado e configurado corretamente para o Enterprise Voice e ter uma política de voz atribuída.

#### <a name="shared-mailbox-is-still-accessible"></a>A caixa de correio compartilhada ainda está acessível

Uma caixa de correio compartilhada configurada usando o Um Online do Exchange continua a receber mensagens após a migração para o TAMBÉM e a ser acessível aos usuários por meio do Outlook. No entanto, o acesso para alterar as mensagens de saudação dessas caixas de correio não estará disponível após a migração para o RECURSO. Os clientes com caixas de correio compartilhadas usadas para capturar chamadores de atendimento automático devem aproveitar os recursos De atendimento automático e caixa de correio compartilhada de filas de chamada depois de lançados (ETA de outubro de 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>A faixa "Nome de usuário não está usando o Skype for Business" é exibida

O serviço DEM é baseado na infraestrutura do Microsoft Teams, e as chamadas de um cliente do Skype for Business podem fazer com que uma faixa de informações seja exibida no cliente que diz: "O nome de usuário não está usando o Skype for Business. Para uma experiência mais rica, mude para o Teams ou inicie uma reunião do Skype."
Certifique-se de atualizar o cliente Skype for Business de seus usuários para a atualização mais recente do cliente C2R para impedir que essa faixa apareça.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurar Caixa Postal" leva você ao OWA

Clicar  em Configurar Caixa Postal do cliente continuará a levar os clientes do Skype for Business Server 2015/2013 para a página de portal do Office Web Access (OWA) após a migração para o SKYPE for Business Server 2013. Todas as configurações foram removidas da guia Caixa Postal no OWA, e uma faixa será exibida com um link de redirecionamento para levar os usuários ao portal de configurações do usuário do VOCÊ.

#### <a name="changing-greeting-remotely"></a>Alterando a saudação remotamente

O acesso de assinante PSTN não é suportado no DEVE. Para usuários que precisam alterar a saudação remotamente, uma opção de menu "Alterar sua saudação" foi adicionada ao serviço IVR da caixa postal para clientes móveis. Os usuários podem chamar esse serviço pressionando e segurando a tecla "1" no teclado de discagem do cliente móvel.
