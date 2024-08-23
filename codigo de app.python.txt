# Definição dos cargos e seus respectivos níveis de acesso
cargos = {
    "gerente": "irrestrito",
    "analista": "dia_util",
    "estagiario": "dia_util"
}

# Definição dos dias da semana e seus respectivos status (útil ou não)
dias_da_semana = {
    "segunda-feira": True,
    "terca-feira": True,
    "quarta-feira": True,
    "quinta-feira": True,
    "sexta-feira": True,
    "sabado": False,
    "domingo": False
}

def controle_de_acesso(cargo, dia_da_semana):
    # Verifica se o cargo existe na lista de cargos
    if cargo not in cargos:
        return "Cargo não encontrado"

    # Verifica se o dia da semana existe na lista de dias da semana
    if dia_da_semana not in dias_da_semana:
        return "Dia da semana não encontrado"

    # Verifica o nível de acesso do cargo
    if cargos[cargo] == "irrestrito":
        return "Acesso permitido"
    elif cargos[cargo] == "dia_util":
        if dias_da_semana[dia_da_semana]:
            return "Acesso permitido"
        else:
            return "Acesso negado (dia não útil)"
    else:
        return "Erro desconhecido"

# Testes
print(controle_de_acesso("gerente", "segunda-feira"))  # Acesso permitido
print(controle_de_acesso("analista", "sabado"))  # Acesso negado (dia não útil)
print(controle_de_acesso("estagiario", "quarta-feira"))  # Acesso permitido
print(controle_de_acesso("desenvolvedor", "segunda-feira"))  # Cargo não encontrado