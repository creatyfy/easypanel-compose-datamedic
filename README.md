# Compose do DataMedic (EasyPanel)

Cópia do template Supabase do EasyPanel com um ajuste: os serviços de log
(`analytics`/Logflare e `vector`) foram removidos.

**Motivo:** o `analytics` não fica saudável num servidor de dois núcleos —
é pesado e espera credenciais do Google Cloud que a clínica não usa. Como
o `studio` declarava dependência dele, a implantação inteira falhava e o
gateway respondia 502, mesmo com banco, autenticação e armazenamento no ar.

O `vector` existe só para alimentar o `analytics`, e nenhum outro serviço
dependia dos dois. A aba de logs do Studio foi desligada para não buscar o
que não existe mais.

Origem: https://github.com/easypanel-io/compose (ramo `18-05-2026`)
