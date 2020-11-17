# OneeToOne

package jason_product_shop.produsct_shop.domain.entity;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.OneToOne;
import javax.persistence.Table;

@Entity
@Table(name = "users")
public class User extends BaseEntity {

    private int age;
    private String firstName;
    private String lastName;
    private Product buyer;
    private Product seller;

    public User() {

    }

    @Column(name = "age")
    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Column(name = "fist_name")
    public String getFirstName() {
        return firstName;
    }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    @Column(name = "last_name")
    public String getLastName() {
        return lastName;
    }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    @OneToOne(mappedBy = "buyer" ,targetEntity = Product.class)
    public Product getBuyer() {
        return buyer;
    }

    public void setBuyer(Product buyer) {
        this.buyer = buyer;
    }

    @OneToOne(mappedBy = "seller" , targetEntity = Product.class)
    public Product getSeller() {
        return seller;
    }

    public void setSeller(Product seller) {
        this.seller = seller;
    }
}
