# Laborator-5
Varianta 9:

Cod 1
#include <iostream>
#include <string>

class Hartie {
public:
    Hartie(const std::string& culoare) : culoare_(culoare) {}

    void afiseazaCuloare() const {
        std::cout << "Culoare hartie: " << culoare_ << std::endl;
    }

private:
    std::string culoare_;
};

class Valori {
public:
    Valori(int valoare) : valoare_(valoare) {}

    void afiseazaValoare() const {
        std::cout << "Valoare: " << valoare_ << std::endl;
    }

private:
    int valoare_;
};

class Actiuni : public Hartie, public Valori {
public:
    Actiuni(const std::string& culoare, int valoare, const std::string& numeActiune)
            : Hartie(culoare), Valori(valoare), numeActiune_(numeActiune) {}

    void afiseazaActiune() const {
        afiseazaCuloare();
        afiseazaValoare();
        std::cout << "Nume actiune: " << numeActiune_ << std::endl;
    }

private:
    std::string numeActiune_;
};

int main() {
    Actiuni act("Albastra", 100, "Imprumut");
    act.afiseazaActiune();

    return 0;
}
b) Cod 2

#include <iostream>
#include <string>

// Clasa de baza
class Obiect {
public:
    Obiect(const std::string& nume) : nume_(nume) {}

    void afiseazaNume() const {
        std::cout << "Nume obiect: " << nume_ << std::endl;
    }

private:
    std::string nume_;
};

// Clasa derivata din Obiect
class Hartie : public Obiect {
public:
    Hartie(const std::string& nume, const std::string& culoare)
        : Obiect(nume), culoare_(culoare) {}

    void arataCuloare() const {
        afiseazaNume();
        std::cout << "Culoare hartie: " << culoare_ << std::endl;
    }

private:
    std::string culoare_;
};

// Clasa derivata din Obiect
class Valori : public Obiect {
public:
    Valori(const std::string& nume, int valoare)
        : Obiect(nume), valoare_(valoare) {}

    void afiseazaValoare() const {
        afiseazaNume();
        std::cout << "Valoare: " << valoare_ << std::endl;
    }

private:
    int valoare_;
};

// Clasa derivata din Valori
class Actiuni : public Valori {
public:
    Actiuni(const std::string& nume, int valoare, const std::string& numeActiune)
        : Valori(nume, valoare), numeActiune_(numeActiune) {}

    void afiseazaActiune() const {
        afiseazaValoare();
        std::cout << "Nume actiune: " << numeActiune_ << std::endl;
    }

private:
    std::string numeActiune_;
};

int main() {
    // Exemplu de utilizare
    Actiuni act("Carte", 100, "Imprumut");
    act.afiseazaActiune();

    return 0;
}






