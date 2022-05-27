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
description: A Microsoft está desativando o serviço Exchange Unified Messaging Online (ExchUMO) até 28 de fevereiro de 2020. Este artigo resume o que os clientes afetados devem saber e fazer para planejar a continuidade dos negócios.
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676363"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte à migração da Unificação de Mensagens do Exchange Online

> [!IMPORTANT]
> **O serviço de Unificação de Mensagens Exchange Online está sem suporte a partir de 28 de fevereiro de 2020, às 17h no Horário do Pacífico. Todas as contas de caixa postal foram migradas para Caixa postal na Nuvem serviço da Microsoft. Qualquer tráfego de atendedor automático restante não será monitorado e poderá ser interrompido a qualquer momento.**

Em referência ao comunicado [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) de 8 de fevereiro de 2019, a Microsoft está desativando o serviço Exchange Unified Messaging Online (ExchUMO) até 28 de fevereiro de 2020. Este artigo oferece um resumo do que os clientes afetados devem saber e fazer para planejar a continuidade dos negócios.

O ExchUMO é implantado pelos clientes para serviços de integração de caixa postal, atendedor automático, Fila de Chamadas e fax. A Microsoft planeja ajudar os clientes a migrar para Sistema de Telefonia serviços que já dão suporte a milhares de clientes no Skype for Business Online e Microsoft Teams.

A caixa postal é principalmente uma migração controlada pela Microsoft; o envolvimento do administrador e/ou o investimento podem ser necessários para um subconjunto de clientes. O atendedor automático é uma migração orientada pelo administrador; você precisará criar novamente as árvores de atendedor automático exchUMO existentes no serviço de nuvem do Atendedor Automático de Nuvem. Os clientes que consomem qualquer um dos recursos exchUMO com um PBX de terceiros não serão migrados para serviços de nuvem do Skype porque não dão suporte a sistemas PBX de terceiros. Um plano de desativação para suporte de terceiros foi anunciado neste [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853), e os clientes nesse modelo de implantação podem migrar seus usuários para uma das plataformas/serviços de Comunicação Unificada da Microsoft ou adquirir uma caixa postal de terceiros e/ou solução de atendedor automático para esses usuários. Não há suporte para a integração de fax nos serviços baseados em nuvem; os clientes precisarão migrar para uma solução de terceiros.

## <a name="who-is-affected"></a>Who é afetado?

Os clientes que usam qualquer um dos seguintes recursos do serviço Exchange Unified Messaging Online são afetados:

- Serviço de caixa postal
- Serviço Atendedor Automático
- Serviço Fila de Chamadas
- Integração de fax

> [!Note]
> Os clientes que estão usando qualquer um dos Exchange Server local com o Unified Messaging não são afetados.

Saiba mais sobre o impacto da experiência do usuário e do administrador no [impacto da experiência do usuário](#user-experience-impact).

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e ajudarão os clientes a migrar com base no plano a seguir.

|Grupo de clientes |Linha do tempo  |Detalhes  |
|---------|---------|---------|
|Clientes que estão prontos para migrar<br><br>Recursos a serem migrados:<br><ul><li>Caixa postal</ul>   |   Março – maio de 2019  |Exemplos:<ul><li>    Clientes com implantação e uso simples de caixa postal<li>Clientes que têm todos os requisitos estabelecidos para a Microsoft executar a migração<ul>|
|Clientes com pré-requisitos<br><br>Recursos a serem migrados:<br><ul><li>Caixa postal<li>Atendedor automático<li>Fila de Chamadas</ul> |  Maio – dezembro de 2019 |Exemplos: <br><ul><li>A configuração híbrida não foi concluída<li>Os números PSTN híbridos não estão configurados</ul>|
|Clientes que exigem envolvimento do administrador & investimento do cliente<br><br>Recursos a serem migrados:<ul><li>Voicemail<li>Atendedor automático<li>Filas de Chamadas<li>Integração de fax</ul>| Até fevereiro de 2020  | Exemplos: <br><ul><li>O serviço ExchUMO é consumido pelo PBX de terceiros<li>Clientes com requisitos de acesso de assinante PSTN<li>Clientes no SFB 2010 (sem suporte)<li>Integração de fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Diretrizes de migração de caixa postal

### <a name="get-informed"></a>Obter informações

Familiarize-se com o [comunicado do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e este artigo para planejar uma migração tranquila para seus usuários. Confira [a caixa Skype for Business caixa postal e as opções](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os Sistema de Telefonia caixa postal.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Estabelecer uma topologia Skype for Business híbrida

Se você não tiver uma topologia Skype for Business híbrida estabelecida, precisará fazer isso para habilitar uma migração suave dos usuários da caixa postal. Consulte [Configurar Skype for Business híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obter mais detalhes.

> [!Note]
> Você não precisa migrar seus usuários online para a migração do serviço de caixa postal. No entanto, para que os usuários locais aproveitem o Sistema de Telefonia caixa postal, uma topologia híbrida deve ser estabelecida.

### <a name="plan-your-auto-attendant-migration"></a>Planejar a migração do atendedor automático

Os administradores podem começar a migrar seus atendedores automáticos do ExchUMO para o atendedor automático de nuvem a qualquer momento. Consulte [Configurar um atendedor automático de nuvem](/microsoftteams/create-a-phone-system-auto-attendant) para obter mais detalhes.

A Microsoft continua a fornecer recursos adicionais de atendedor automático que os clientes podem considerar necessários para a migração. Os administradores devem avaliar o conjunto de recursos e migrar suas instâncias de atendedor automático adequadamente. Para obter uma comparação de lista de recursos, consulte a matriz de recursos de serviços baseados em nuvem do [ExchUMO e do Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planejar a validação e o teste da caixa postal após a migração

A migração da caixa postal é orientada pela Microsoft. Os administradores não precisam fazer nada, considerando que a topologia híbrida pré-requisito foi estabelecida. A Microsoft executa a validação e os testes necessários para garantir que a migração da caixa postal dos usuários não seja interrompida. Os administradores são incentivados a executar testes e validação em seu lado. Consulte [o plano de teste sugerido e a validação pós-migração para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) para obter um plano de teste recomendado.

> [!Note]
> Não há suporte para o Lync Server 2010. Se você estiver em uma implantação de servidor 2010, planeje uma atualização do servidor ou considere migrar seus usuários para Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Monitorar o centro Administração de notificação

Observe um aviso no Centro de Administração de Notificação com mais detalhes e uma linha do tempo sobre a migração dos usuários. As notificações são enviadas pelo menos 30 dias antes do período de migração.

> [!Note]
> Se você recebeu uma notificação com a linha do tempo de migração dos usuários e gostaria de adiar sua migração por um motivo comercialmente crítico, entre em contato com Suporte da Microsoft. Você não pode adiar sua migração além da data de desativação de 28 de fevereiro de 2020. Para clientes que podem ter mais perguntas, entre em contato com sua equipe de conta ou Suporte da Microsoft. Os clientes que já Microsoft 365 ou Office 365 podem enviar um caso de suporte por meio do Centro de administração do Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Considere aceitar uma migração planejada

Você pode aceitar uma migração planejada do serviço de Caixa Postal para o SQL. Antes de aceitar, examine os detalhes deste artigo, especialmente as seções a seguir:

- Etapas de migração (esta seção)
- Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure
- Impacto na experiência do usuário

Ao escolher uma migração gerenciada, você não receberá uma notificação de 30 dias de pré-migração no Microsoft 365 de mensagens do portal de administração.

Para aceitar uma migração planejada, envie uma solicitação de email do endereço de email do administrador para [cvm@microsoft.com com as](mailto:cvm@microsoft.com) seguintes informações:

- Data preferencial (terças-feiras): as ondas de migração são executadas todas as terças-feiras. Selecione uma data em uma terça-feira que não esteja além de 3/12/2019.
 
- ID do locatário: número de 32 caracteres neste formato 0046728c-688a-4472-a38f-098fec60ac6x. Você pode encontrar sua ID de locatário no portal de administração do Microsoft 365 em Azure AD ou usando o seguinte cmdlet do PowerShell:`Get-CsTenant | Select ObjectId`

Você receberá uma confirmação por email depois que seu locatário for migrado com êxito.

## <a name="auto-attendant-migration-guidelines"></a>Diretrizes de migração do atendedor automático

os administradores da organização do Microsoft 365 e do Office 365 devem criar novamente seus atendedores automáticos do Exchange UM Online no serviço Microsoft Cloud Auto Attendant e alternar seus números de telefone locais para eles antes da data de desativação do serviço UMO do Exchange de 28 de fevereiro de 2020. Essa é a diretriz recomendada para migrar e testar com êxito novos atendedores automáticos de nuvem. Se você tiver um grande número de atendedores automáticos, poderá usar os [scripts](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) de Migração do Atendedor Automático de Um Exchange para o Atendedor Automático de Nuvem para simplificar a migração em massa de atendedores automáticos.

### <a name="auto-attendant-setup"></a>Configuração do atendedor automático

É altamente recomendável que você inicie a configuração de seus novos atendedores automáticos mais cedo para evitar problemas de última hora e se familiarizar com a funcionalidade e a experiência do serviço Atendedor Automático de Nuvem. Para atendedores automáticos que exigem um ou mais recursos de lacuna, você pode criar e testar os atendedores automáticos quando os recursos de lacuna estão disponíveis para se preparar para a implantação. Para obter mais informações sobre os recursos de lacuna, consulte o [Apêndice](#appendix).

1. Use os Exchange cmdlets UMO para exportar a configuração de atendedores automáticos existentes usando [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Use o cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) no Exchange Online PowerShell para exportar os arquivos de mídia de saudação (se usados) e convertê-los .mp3 formato.

3. Siga as instruções nos atendedores [automáticos do Plan Cloud](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e configure um atendedor automático de nuvem para criar atendedores automáticos usando o centro de administração do Microsoft Teams ou o PowerShell.[](/microsoftteams/create-a-phone-system-auto-attendant)

4. Examine suas saudações se as opções de menu foram alteradas.

5. Configure transferências para seus grupos de resposta usando a solução alternativa "Transferência automática de chamada do atendedor para PSTN[](#known-issues)" na seção Problemas conhecidos deste artigo.  

6. Teste os novos atendedores automáticos chamando-os internamente ou atribuindo um número de telefone de teste.  

### <a name="cutover"></a>Substituição

1. Alterne seus números de Exchange atendedores automáticos UMO para os novos atendedores automáticos.
2. Mova o URI SIP do objeto de contato para a conta de recurso.
3. Teste e valide seus atendedores automáticos usando os números de telefone atribuídos recentemente.

## <a name="appendix"></a>Apêndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure

| Serviço | Nível de recurso | Recurso | Observações  | VM/AA de nuvem  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Recursos de serviço| Suporte a PBX de terceiros    | Incluindo todos os recursos fornecidos ao PBX de terceiros, como MWI (Indicador de Espera de Mensagens) usando mensagens de notificação SIP de Exchange UM Online | N   | S    |
| VM | Recursos de serviço  | Suporte Skype for Business Server   |  | S | S    |
| VM | Recursos de serviço | Suporte Microsoft Teams|  | Y | N    |
| VM | Recursos de serviço | Descoberta Eletrônica e Retenção  | Para segurança e conformidade  | S | S    |
| VM | Recursos de serviço | Exchange regras de segurança | Para segurança e conformidade  | S | S    |
| VM | Recursos do usuário | Acesso de discagem PSTN  | Acesso de assinante  | N | S    |
| VM | Recursos do usuário | Delegar  | email de chamada perdida  | N | S    |
| VM | Recursos do usuário | PSTN Outlook Voice Access   | Acesso de assinante  | N | S    |
| VM | Recursos do usuário | Discar usando um ponto de extremidade autenticado | Chamar o serviço de caixa postal para ouvir mensagens de voz e alterar as configurações de caixa postal| S | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a caixa postal   |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar a saudação pessoal  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para criar uma saudação OOF  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para substituir a saudação padrão pelo TTS  |  | Y | N    |
| VM | Recursos do usuário | Gravar saudações pessoais (dispositivo autenticado) |  | S | S    |
| VM | Recursos do usuário | Gravar saudações pessoais (PSTN) — reproduzir no telefone |  | N | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a transcrição |  | N | S    |
| VM | Recursos do usuário | Transcrição  |  | S | S    |
| VM | Recursos do usuário | MWI (Indicador de Espera de Mensagem) usando mensagens de notificação SIP |  | N | S    |
| VM | Recursos do usuário | Formato de arquivo de áudio MP3 Outlook    |  | S | S    |
| VM | Recursos do usuário | Controle de reprodução de velocidade variável |  | S | S    |
| VM | Recursos do usuário | Encaminhar uma caixa postal  | Encaminhar uma caixa postal recebida para outros usuários | S | S    |
| VM | Recursos do usuário | Enviando uma mensagem de voz para um grupo de usuários  |Transmissão de caixa postal   | N | S   |
| VM | Recursos do usuário | Notificação de caixa postal usando SMS    | Os usuários podem receber uma SMS quando tiverem uma nova caixa postal    | N | S    |
| VM | Recursos do usuário | Idiomas de saudação com suporte | Detalhes aqui: [O que são atendedores automáticos de nuvem?](/microsoftteams/what-are-phone-system-auto-attendants) | S | S    |
| VM | Recursos do usuário | Regras de atendimento de chamada |  | S | S    |
| VM | Recursos do usuário | Reproduzir no telefone (PSTN) – para reproduzir mensagem | Ligue-me no meu celular para ouvir a mensagem de voz  | N | S    |
| VM | Recursos do usuário | Reproduzir no telefone (Autenticação) – para reproduzir mensagem | Ligue-me no meu dispositivo autenticado  | N | S    |
| VM | Recursos do usuário | Caixa de correio compartilhada entre vários usuários |  | S | S    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal protegida | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegida| N | S    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal privada | O chamador pode escolher uma opção para marcar uma mensagem gravada como privada  | N | S    |
| VM | Recursos do chamador  | Detecção de silêncio   |  | N | S    |
| VM | Tenant-Admin recursos | Caixa postal protegida no nível do servidor    | O administrador de locatários pode configurar uma regra de nível de serviço para marcar a caixa postal de entrada como protegida | S | S    |
| VM | Tenant-Admin recursos | Alterar o limite de tempo de duração da gravação  |     | S | S    |
| VM | Tenant-Admin recursos | Alterar o tempo limite de detecção de silêncio    |  | N/D    | Y    |
| VM | Tenant-Admin recursos | Alterar o número de falhas de entrada | VALOR: embutido em código para 3 | N | Y    |
| VM | Tenant-Admin recursos | Alterar o idioma padrão |  | S | S    |
| VM | Tenant-Admin recursos | Desabilitar/habilitar transcrição |  | S | S    |
| VM | Tenant-Admin recursos | Desabilitar/habilitar notificação de chamada perdida |  | N | S    |
| VM | Tenant-Admin recursos | Ajude a Microsoft a melhorar a visualização da caixa postal    |  | S | S    |
| VM | Tenant-Admin recursos | Personalizar mensagem de texto para usuários habilitados|  | N/D    | Y    |
| VM | Tenant-Admin recursos | Mascaramento de profanidade de transcrição|  | Y | N    |
| VM | Tenant-Admin recursos | Política de caixa postal    |   | S | S    |
| VM | Tenant-Admin recursos | Administração do portal da Web   |  | CY19   | S    |
| VM | Tenant-Admin recursos | PowerShell   |  | S | S    |
| UM | Recursos do usuário | MWI (Indicador de Espera de Mensagem) Skype for Business certificados   |Pode ser fornecido pelo parceiro de telefone  | Não | Sim    |
| AA | Recursos de serviço | Suporte a AA PBX de terceiros    |  | N | S    |
| AA | Recursos de serviço | Suporte Skype for Business Server   |  | S | S    |
| AA | Recursos de serviço | Suporte Microsoft Teams|  | Y | N    |
| AA | Recursos de serviço | Discar por nome, entrada DTMF    |  | S | S    |
| AA | Recursos de serviço | Discar por nome, entrada de fala  |  | S | S    |
| AA | Recursos de serviço | Suporte a vários idiomas | Detalhes do idioma aqui: [O que são atendedores automáticos de nuvem?](/microsoftteams/what-are-phone-system-auto-attendants) | S | S    |
| AA | Recursos de serviço | Transferir para operador, CQ ou um usuário |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN internamente (DID RNL)  |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN externamente  |  | Confira a seção Problemas Conhecidos abaixo | Y    |
| AA | Recursos de serviço | Horário comercial |  | S | S    |
| AA | Recursos de serviço | Opções de menu | Opções do menu IVR  | S | S    |
| AA | Recursos de serviço | Atribuindo um número PSTN de nuvem ao AA |  | Y | N    |
| AA | Recursos de serviço | Atribuindo um número PSTN local ao AA  |  | S | S    |
| AA | Recursos de serviço | Seleção de usuário personalizada  | Habilitando os chamadores a acessar a lista personalizada de usuários da organização| S | S    |
| AA | Recursos de serviço | Tratamento de horas extras e feriados  |  | S | S    |
| AA | Recursos de serviço | Saudação personalizada usando conversão de texto em fala  |  | S | S    |
| AA | Recursos de serviço | Discagem de ramal   | Alcançando um usuário discando sua extensão  | S   | S    |
| AA | Recursos de serviço | Caixa de correio para os chamadores do AA deixarem uma mensagem    |  | S   | S    |
| AA | Recursos de serviço | Várias atribuições de número PSTN para um AA|  | S | S    |
| AA | Tenant-Admin recursos | Administração do portal da Web   |  | Y | N    |
| AA | Tenant-Admin recursos | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos de serviço | Integração de fax|  | N | S    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação pós-migração para administradores

Para validar se os usuários foram migrados para o Caixa postal na Nuvem, deixe uma caixa postal para um usuário e verifique o corpo da mensagem Outlook. Caixa postal na Nuvem mensagens têm um rodapé que lê:

"Obrigado por usar a Transcrição! Se você não vir uma transcrição acima, é porque a qualidade do áudio não foi clara o suficiente para transcrever."

Ao testar a funcionalidade de caixa postal após a migração dos usuários, considere os seguintes cenários:

- Valide o acesso à caixa postal em todos os tipos de ponto de extremidade em sua organização, como aplicativos e telefones IP.
- Valide com usuários de exemplo que as saudações personalizadas configuradas são tocadas para os chamadores.
- Se sua organização tiver um requisito legal ou de conformidade para desabilitar a transcrição para os usuários, verifique se ela está desabilitada após a migração. Para obter mais detalhes, [consulte Configurar Caixa postal na Nuvem](/microsoftteams/set-up-phone-system-voicemail).
- Se você configurou anteriormente Exchange regras e políticas de VM, verifique se elas são eficazes.
- Familiarize-se com os cmdlets do PowerShell do serviço Caixa postal na Nuvem para alterar as configurações do usuário.  

### <a name="user-experience-impact"></a>Impacto na experiência do usuário

A seguir está uma visão geral da experiência de migração de caixa postal do usuário final.


|Experiência  |Alteração na experiência do usuário|
|---------|---------|
|Notificação por email | Sem alteração<br>Nenhum email é enviado aos usuários notificando-os sobre a ativação/migração da conta de caixa postal. |
|Acesso a mensagens anteriores | Sem alteração<br>Os usuários têm acesso às mensagens de voz anteriores em todos os pontos de extremidade com suporte. |
|Recebendo VM no Outlook, aplicativos SFB| Sem alteração<br>Os usuários continuam recebendo suas mensagens de caixa postal em todos os pontos de extremidade com suporte. |
|Transcrição | Reforçada<br>A transcrição DE TRANSCRIÇÃO tem uma taxa de precisão muito maior e idiomas com suporte do que o ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários podem alterar suas preferências de um Portal de Configuração do Usuário (USP). Os usuários podem acessar a USP por meio de um hiperlink no email da caixa postal ou no User-Settings no cliente SFB; https://aka.ms/vmsettings.
 |Recursos| Consulte a comparação do conjunto de recursos para obter detalhes. |
|Outlook regras para mensagens de VM | Sem alteração<br>As regras criadas anteriormente serão aplicadas a mensagens DE VALOR após a migração.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento e provisionamento de usuários noVISION

Novos Skype for Business usuários serão provisionados automaticamente para a caixa postal na nuvem quando criados. Nenhum trabalho ou licença adicional de administrador é necessário para provisionar novos usuários de caixa postal. Consulte [Configurar o Caixa postal na Nuvem](/microsoftteams/set-up-phone-system-voicemail) para saber mais sobre o gerenciamento de políticas para usuários novos e existentes.

### <a name="admin-auto-attendant-management-experience"></a>Administração de gerenciamento do Atendedor Automático

Para saber mais sobre atendedores automáticos, consulte [Configurar um atendedor automático de nuvem](/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Problemas conhecidos

#### <a name="greeting-inconsistencies"></a>Inconsistências de saudação

O acesso de assinante pode continuar a funcionar para seu locatário até que o serviço seja completamente desativado, mesmo depois que todos os usuários tiverem sido migrados para o Caixa postal na Nuvem. Para evitar confusão do usuário e uma experiência inconsistente, desabilite o acesso do assinante, pois as saudações mudam após a migração. Para fazer isso, remova o contato EXUM para cada linha de acesso do assinante usando `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Transferência automática de chamada de atendedor para PSTN

Para transferir uma chamada de atendedor automático para um número de telefone PSTN externo via Skype for Business Server ou um serviço de Grupo de Resposta (RGS) no Skype for Business Server, crie um novo usuário local com encaminhamento de chamadas definido como o número de telefone PSTN ou o número de telefone RGS. O usuário deve estar habilitado e configurado corretamente para Enterprise Voice e ter uma política de voz atribuída.

#### <a name="shared-mailbox-is-still-accessible"></a>A caixa de correio compartilhada ainda está acessível

Uma caixa de correio compartilhada configurada usando Exchange UM Online continua a receber mensagens após a migração para a FABRIC e ser acessível aos usuários por meio de Outlook. No entanto, o acesso para alterar as mensagens de saudação dessas caixas de correio não estará disponível após a migração para o VALOR. Os clientes com caixas de correio compartilhadas que são usadas para capturar chamadores de atendedor automático devem aproveitar os recursos atendedores automáticos e filas de chamadas de caixa de correio compartilhada após o lançamento (ETA outubro de 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>A faixa "Nome de usuário não está Skype for Business" é exibida

O serviço DODS baseia-se na infraestrutura do Microsoft Teams e as chamadas de um cliente do Skype for Business podem fazer com que uma faixa de informações seja exibida no cliente que diz: "O nome de usuário não está usando Skype for Business. Para obter uma experiência mais rica, alterne para Teams ou inicie uma Skype reunião."
Certifique-se de atualizar o cliente Skype for Business seus usuários para a atualização mais recente do cliente C2R para impedir que essa faixa seja exibida.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurar Caixa Postal" leva você ao OWA

Clicar em  Configurar Caixa Postal do cliente continuará levando os clientes do Skype for Business Server 2015/2013 para a página do portal do Office Web Access (OWA) após a migração para a OFFLINE. Todas as configurações foram removidas da guia Caixa Postal no OWA e uma faixa será exibida com um link de redirecionamento para levar os usuários para o portal de configurações do usuário DO VALOR.

#### <a name="changing-greeting-remotely"></a>Alterando a saudação remotamente

O acesso de assinante PSTN não é compatível com a LTDA. Para usuários que precisam alterar a saudação remotamente, uma opção de menu "Alterar sua saudação" foi adicionada ao serviço IVR da caixa postal para clientes móveis. Os usuários podem chamar esse serviço pressionando e segurando a tecla "1" no teclado de discagem do cliente móvel.